+++
lang="en-GB"
title="Fuzzing the GuruxDLMS.c library with AFL"
date="2019-11-28"
author="Maciej Miszczyk"
image="/blog/Seqred_fuzzing.jpg"
tags=['fuzzing']
+++

## Fuzzing - methods of looking for security-related bugs

**Fuzzing (fuzz testing)** is one of the most popular methods of looking
for security-related bugs, especially the ones related to memory access
(e.g. buffer overflow, use after free). Those are the potentially most
dangerous bugs in software written in languages that are compiled to
machine code (e.g. C and C++), in worst case scenario allowing the
attacker to completely take over the execution of a vulnerable program.

Fuzzing is based on a very simple idea: we provide the program that we
want to test with randomized input data, and look for inputs that cause
it to crash (in Unix-like systems it is usually indicated by a SEGV
signal, which is sent when by the operating system when the program
attempts an invalid access to a protected memory region -- e.g. writing
to a read-only page). However, modern smart fuzzers are more than just
random number generators: they aim to maximize code coverage by using
instrumentation (which supplies the fuzzer with data about locations in
code which were visited during the execution of a tested program) and
genetic algorithms (which causes newly generated data to be more similar
to what previously allowed the fuzzer to reach new locations).

In this article, we'll show an example of using a smart fuzzer called
AFL to find vulnerabilities in an open-source library GuruxDLMS.c. The
library implements a DLMS protocol, which is used in the electric sector
for remote readings of energy meters. Our attack scenario assumes that
the attacker attempts to connect to the GuruxDLMS.c-based server (energy
meter) to either disrupt its operation or to take over its execution
(e.g. to falsify its readings).

In the GuruxDLMS.c source repository, there's a
GuruxDLMSSimpleServerExample directory containing an example
implementation of an energy meter. From reading the main() function, we
can notice that it works by redirecting each byte sent to it over TCP
4061 port to the svr_handleRequest3() function.

#if defined(\_WIN32) \|\| defined(\_WIN64)//Windows includes

int \_tmain(int argc, \_TCHAR\* argv\[\])

#else

int main(int argc, char\* argv\[\])

#endif

{

    unsigned char data;

    struct sockaddr_in client;

    int ret, ls, s;

    struct sockaddr_in add = { 0 };

#if defined(\_WIN32) \|\| defined(\_WIN64)//If Windows

    int len;

    int AddrLen = sizeof(add);

#else //If Linux

    socklen_t len;

    socklen_t AddrLen = sizeof(add);

#endif

#if defined(\_WIN32) \|\| defined(\_WIN64)//Windows includes

    WSADATA wsaData;

    if (WSAStartup(MAKEWORD(2, 2), &wsaData) != 0)

    {

        // Tell the user that we could not find a usable WinSock DLL.

        return 1;

    }

#endif

    bb_init(&reply);

    //Start server using logical name referencing and HDLC framing.

    svr_init(&settings, 1, DLMS_INTERFACE_TYPE_HDLC, HDLC_BUFFER_SIZE,
PDU_BUFFER_SIZE, frame, HDLC_BUFFER_SIZE, pdu, PDU_BUFFER_SIZE);

    //Add COSEM objects.

    svr_InitObjects(&settings);

    //Start server

    if ((ret = svr_initialize(&settings)) != 0)

    {

        //TODO: Show error.

        return 1;

    }

    ls = socket(AF_INET, SOCK_STREAM, 0);

    add.sin_port = htons(4061);

    add.sin_addr.s_addr = htonl(INADDR_ANY);

    add.sin_family = AF_INET;

    if ((ret = bind(ls, (struct sockaddr\*) &add, sizeof(add))) == -1)

    {

        return -1;

    }

    while (1)

    {

        if ((ret = listen(ls, 1)) == -1)

        {

            //socket listen failed.

            return -1;

        }

        len = sizeof(client);

        s = accept(ls, (struct sockaddr\*)&client, &len);

        while (1)

        {

            //Read one char at the time.

            if ((ret = recv(s, (char\*)&data, 1, 0)) == -1)

            {

#if defined(\_WIN32) \|\| defined(\_WIN64)//If Windows

                closesocket(s);

                s = INVALID_SOCKET;

#else //If Linux

                close(s);

                s = -1;

#endif

                break;

            }

            //If client closes the connection.

            if (ret == 0)

            {

#if defined(\_WIN32) \|\| defined(\_WIN64)//If Windows

                closesocket(s);

                s = INVALID_SOCKET;

#else //If Linux

                close(s);

                s = -1;

#endif

                break;

            }

            if (svr_handleRequest3(&settings, data, &reply) != 0)

            {

#if defined(\_WIN32) \|\| defined(\_WIN64)//If Windows

                closesocket(s);

                s = INVALID_SOCKET;

#else //If Linux

                close(s);

                s = -1;

#endif

                break;

            }

            if (reply.size != 0)

            {

                if (send(s, (const char\*)reply.data, reply.size --
reply.position, 0) == -1)

                {

#if defined(\_WIN32) \|\| defined(\_WIN64)//If Windows

                    closesocket(s);

                    s = INVALID_SOCKET;

#else //If Linux

                    close(s);

                    s = -1;

#endif

                    break;

                }

                bb_clear(&reply);

            }

        }

    }

#if defined(\_WIN32) \|\| defined(\_WIN64)//Windows

    WSACleanup();

#if \_MSC_VER \> 1400

    \_CrtDumpMemoryLeaks();

#endif

#endif

    return 0;

}

By default, AFL works by providing the tested program with the path to a
generated file. For this reason, we'll rewrite the example application
so that instead of listening on a TCP port, it will read from a file
pointed by argv\[1\]. The rest of the program logic will remain
unchanged: each input byte will be passed to the existing
svr_handleRequest3() function -- this will make sure that the only thing
changed between the original and our modified version is how the program
receives its input data.

// GuruxDLMSSimpleServerExample/src/main.c

int main(int argc, char \*\*argv){

  unsigned char data;

  FILE \*f;

  if(argc \< 2){

    puts("Error. Please provide a filename");

    return 1;

  }

  svr_init(&settings, 1, DLMS_INTERFACE_TYPE_HDLC, HDLC_BUFFER_SIZE,

           PDU_BUFFER_SIZE, frame, HDLC_BUFFER_SIZE, pdu,
PDU_BUFFER_SIZE);

  svr_InitObjects(&settings);

  if(svr_initialize(&settings)){

    puts("Server init error");

    return 2;

  }

  if(!(f = fopen(argv\[1\], "rb"))){

    puts("Error reading file");

    return 3;

  }

  while(fread(&data, sizeof(unsigned char), 1, f)){

    if(svr_handleRequest3(&settings, data, &reply)){

      puts("Error when handling request");

      break;

    }

    if(reply.size != 0){

      printf("Server reply: %s\\n", reply.data);

      bb_clear(&reply);

    }

  }

  puts("EOF");

  fclose(f);

  return 0;

}

Now we can compile our program with AFL instrumentation. To make
analysis easier, we will also use ASAN (Address Sanitizer) to stop the
execution of the program at first invalid memory access. ASAN will also
show us the location of faulty code, and it will tell us where to find
the code which first allocated the memory.

To compile with AFL and ASAN, we must modify development/makefile and
GuruxDLMSSimpleServerExample/makefile. We need to change the compiler
(CC variable) from default gcc to afl-clang. We must also append the
-fsanitize=address flag CFLAGS to LFLAGS in both files. After making
those changes, we'll build our test program with the commands below:

cd development

make

cp lib/libgurux_dlms_c.a ../GuruxDLMSSimpleServerExample/obj/

cd ../GuruxDLMSSimpleServerExample

make

The output binary can be found in
GuruxDLMSSimpleServerExample/bin/gurux.dlms.simple.server.bin. Now we
only need input and output directories to start fuzzing. We can create
them by executing those commands:

mkdir input

mkdir output

While the contents of the second directory will be generated by AFL, the
first one should contain examples of correct input data which will be
used to create potentially dangerous files. But what if we have no such
examples? We just need patience: thanks to its genetic algorithm, AFL
will eventually generate valid DLMS packets even if at first it has only
a single whitespace character to work with.

echo ' ' \> input/1

Now we have everything we need to start fuzzing. To run AFL, we have to
execute the following command:

afl-fuzz -i input/ -o output/ bin/gurux.dlms.simple.server.bin @@

What does the mysterious „@@" string mean? This is just a placeholder
which will be replaced by the path to a generated input file. Why do we
have to do that? We need to remember that not every program will receive
path to input file in argv\[1\]. Some of them might need a command-line
flag, for example --input-file @@.

![](/blog/Fuzzowanie_1.jpg)

After a few hours of fuzzing, it is clear that the results are not
satisfactory: the fuzzer fails to find new paths through code, and it
never managed to crash the tested program. Why? The DLMS protocol uses
checksums to verify the integrity of received packets. Even smart
fuzzers based on genetic algorithms aren't yet able to calculate valid
checksums and put them in a required location.

A possible solution would be a script which understand the structure of
DLMS packets and fixes checksums (this would be necessary if we wanted
to use AFL's output in real-life attacks). One of the tools we could use
for this is AFL post_library which can perform post-processing on files
generated by the fuzzer. We'll choose a simpler solution: disable
checksum verification in source code, recompile the program and start
fuzzing again.

// development/src/dlms.c

int dlms_getHdlcData(

    unsigned char server,

    dlmsSettings \* settings,

    gxByteBuffer \* reply,

    gxReplyData \* data,

    unsigned char\* frame,

    unsigned char preEstablished,

    unsigned char first)

{

    //(...)

    crc = countCRC(reply, packetStartID + 1,

        reply-\>position -- packetStartID -- 1);

    if ((ret = bb_getUInt16(reply, &crcRead)) != 0)

    {

        return ret;

    }

 /\*   if (crc != crcRead)

    {

        if (reply-\>size -- reply-\>position \> 8)

        {

            return dlms_getHdlcData(server, settings, reply, data,
frame, preEstablished, first);

        }

        return DLMS_ERROR_CODE_WRONG_CRC;

    }\*/

    // Check that packet CRC match only if there is a data part.

    if (reply-\>position != packetStartID + frameLen + 1)

    {

        crc = countCRC(reply, packetStartID + 1, frameLen -- 2);

        if ((ret = bb_getUInt16ByIndex(reply, packetStartID + frameLen
-- 1, &crcRead)) != 0)

        {

            return ret;

        }

       /\* if (crc != crcRead)

        {

            return DLMS_ERROR_CODE_WRONG_CRC;

        }\*/

        //(...)

![](/blog/Fuzzowanie_2.jpg)

As can be seen, we have managed to find crashing inputs. Let's see what
happens when we manually pass one of them to the tested program:

==10691==ERROR: AddressSanitizer: stack-buffer-overflow on address
0x7fffffffd5c1 at pc 0x7ffff6ee2397 bp 0x7fffffffd510 sp 0x7fffffffccb8\
READ of size 8187 at 0x7fffffffd5c1 thread T0\
    #0 0x7ffff6ee2396 in \_\_asan_memcpy
(/usr/lib/x86_64-linux-gnu/libasan.so.4+0xc8396)\
    #1 0x55555564b551 in ba_copy src/bitarray.c:203\
    #2 0x55555568d1c7 in apdu_parseProtocolVersion src/apdu.c:1067\
    #3 0x55555568e864 in apdu_parsePDU src/apdu.c:1428\
    #4 0x5555556aca38 in svr_HandleAarqRequest src/server.c:325\
    #5 0x5555556c22a3 in svr_handleCommand src/server.c:2398\
    #6 0x5555556c494f in svr_handleRequest2 src/server.c:2700\
    #7 0x5555556c6333 in svr_handleRequest3 src/server.c:2467\
    #8 0x555555695dff in main src/main.c:479\
    #9 0x7ffff648db96 in \_\_libc_start_main
(/lib/x86_64-linux-gnu/libc.so.6+0x21b96)\
    #10 0x5555555603b9 in \_start
(/home/afl/fuzzer/gurux.dlms.simple.server.bin+0xc319)

Looking at the source code of functions appearing in the stack trace, we
can quickly locate the root cause of our crash: if the value of
unusedBits variable (which is read from input file) is greater than 8,
integer overflow causes the value passed to the ba_copy() function to be
greater than the size of a source array. This means that we're dealing
with an out-of-bounds read vulnerability.

// development/src/apdu.c

int apdu_parseProtocolVersion(dlmsSettings\* settings,

    gxByteBuffer\* buff)

{

    //(...)

    if ((ret = bb_getUInt8(buff, &unusedBits)) != 0)

    {

        return ret;

    }

    //(...)

    bitArray bb;

    ba_init(&bb);

    ba_copy(&bb, &value, 8 -- unusedBits);

    //(...)

}

How serious is our bug? It seems that data copied from outside of the
buffer is never sent anywhere (which means that it's not a vulnerability
as dangerous as the famous OpenSSL Heartbleed bug), but we can notice
that even if we compile the test program without AFL and ASAN
instrumentation, we still have a segmentation fault. This means that the
attacker could use this vulnerability to disrupt the meter's operation
-- and analysis of the source code shows, that even if password is
needed to establish a connection, the vulnerable function is entered
before it can be verified. This means that it's an unauthenticated
denial of service bug.

The described vulnerability is, of course, not present in recent
versions of the library: we have reported it (as well as all the other
bugs we have identified during the fuzzing process) to the developers
and made sure that it has been fixed before publishing this article.
However, a lot of the software that we're using everyday -- including
the software that is running on industrial systems -- can still be
vulnerable to such attacks (or worse). It can also be useful to verify
the security of libraries we're including in software we write -- and if
we have access to source code (as is the case with the open-source
GuruxDLMS.c library), we could also use some of our time and processor
cycles to perofrm fuzzing.