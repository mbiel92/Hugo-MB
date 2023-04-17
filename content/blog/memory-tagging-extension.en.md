+++
lang="en-GB"
title="Memory Tagging Extension"
date="2019-02-25"
author="@tals0n0r"
image="/blog/red.jpg"
tags=['memory tagging', 'procesors']
+++

> ### In Q4 2018 ARM announced new architecture Armv8.5-A. One of the introduced features is Memory Tagging Extension (MTE): hardware supported memory tagging. What is the purpose of MTE feature?

Most of security vulnerabilities in C/C++ are caused by memory safety bugs related to buffer overruns, use-after-free and uninitialized memory errors. Let’s see what that errors are and what are the implications of their occurrence.


Buffer overruns refer to an instance where a program tries to access memory beyond its intended range. Most of famous security issues You may heard about were **linear buffer overflows:**  
[– Heartbleed](http://heartbleed.com)  
[– Total Meltdown](https://nvd.nist.gov/vuln/detail/CVE-2018-1038)  
[– GHOSTBug](https://nvd.nist.gov/vuln/detail/CVE-2015-0235)  
[– Venom](https://venom.crowdstrike.com/)

Latest Chrome issues:  
[– CVE-2018-6153](https://www.cvedetails.com/cve/CVE-2018-6153/)  
[– CVE-2018-6120](https://www.cvedetails.com/cve/CVE-2018-6120/)

Some kernel bugs:  
[– CVE-2018-14633](https://www.cvedetails.com/cve/CVE-2018-14633/)  
[– CVE-2018-12233](https://www.cvedetails.com/cve/CVE-2018-12233/)

**Use-after-free** occur when a program accesses memory after it has freed it for reuse:  
[– CVE-2018-16065](https://www.cvedetails.com/cve/CVE-2018-16065/)  
[– CVE-2018-17182](https://www.cvedetails.com/cve/CVE-2018-17182/)  
[– CVE-2018-10879](https://www.cvedetails.com/cve/CVE-2018-10879/)

**Uninitialized memory** issue may lead to memory disclosure:  
[– CVE-2017-5103](https://www.cvedetails.com/cve/CVE-2017-5103/)  
[– CVE-2017-5102](https://www.cvedetails.com/cve/CVE-2017-5102/)  
[– Red Hut Bugzilla](https://bugzilla.redhat.com/show_bug.cgi?id=1584043)

> ### Memory sanitizers

There are few tools able to find memory safety bugs. The oldest one is widely known **Valgrind** and its **Memcheck**, that came into public view in late February 2002. Second one, **AdressSanitizer (ASAN)** was introduced to LLVM 3.1 and GCC 4.8 compilers by Google in 2011. ASAN will handle stack and heap-based buffer overflows, stack-based use-after-free, use-after-return and use-after-scope. Another tool called **Memory Sanitizer (MSan)** can be used for uninitialized memory check. For linux kernel **kmemcheck** and **kasan** were introduced accordingly.

Usage of the software-based sanitizers has few significant drawbacks: they maintain shadow memory for application memory, redzones and quarantines around stack, heap and global objects. Such implementations are memory and cpu hungry, also significantly increases size of binaries because of compiler instrumentation. Therefore, mentioned sanitizers are used only during testing phase and as support tools while performing security assessment, fuzzing and security hardening: never in the production nor release binaries.

> ### Memory tagging

Another approach is memory tagging. In this solution, bytes of memory aligned by TG (tagging granularity) gets his own tag of size TS (tag size). Tag bits are placed in the unused bits in every pointer. In Aarch64 up to 8 most significant bits of a 64-bit pointer as are allowed to be a tag value thanks to TBI (top byte ignore). When we allocate memory using malloc, tag is set to entire chunk of memory and into the corresponding pointer. During the load and store operation to that memory tags are validated, on mismatch exception is raised. This allows to catch most of memory safety bugs like stack and heap-based buffer overflow and use-after-free.

Let’s consider heap allocation of 20 bytes with TS 4 bits and TG 16 bytes (Fig 1).

![](/blog/Memory_tagging_1.jpg)

20 bytes needs to be allocated, memory allocator aligns it to the 32 bytes cause of 16 bytes TG. Next allocator chooses a tag (marked green), and places it in the 4 most significant bits of pointer and the memory. While dereferencing pointer p at position 32, tag values will not correspond between pointer and memory, heap-based buffer overflow will be caught (Fig 2). Note that because of 16 bytes TG, deference at 20 byte will be not detected due to the same tag value.

![](/blog/Memory_tagging_2a.jpg)

Pretty similar situation will occur during deallocation. While deleting previously allocated heap chunk, it will be re-tagged (re-colored). After deallocation, if there is still a dangling pointer (green) pointing to invalid memory (re-colored to red), while dereference use-after-free will be catched (Fig 3).

![](/blog/Memory_tagging_3a.jpg)

Memory tagging is implemented in Clang/ LLVM toolchain, it is called **HWSAN** (hardware-assisted address sanitizer). It works on Aarch64 with TBI feature ( top-byte-ignore), with 8-bit TS and 16-bytes TG. As tag validation is performed by compiler instrumentation during runtime, there is still some overhead to cpu and binary size (2x), but memory consumption is very low (6%).

To address security mitigations related to memory safety bugs ARM decided to introduce Memory Tagging Extension, hardware implementation of memory tagging with TS of 4 bits and TG of 16 bytes. Instruction set was expanded by 15 new instructions:

![](/blog/Memory_tagging.jpg)

> ### What is next?

Waiting. Despite initial support for memory tagging extension has been already introduced to [GCC 9](https://gcc.gnu.org/git/?p=gcc.git;a=commit;h=3a861b7b9e2c3652dcbe8b44434650429199df56) and [LLVM](https://reviews.llvm.org/D52490), some compilers optimizations must be made. Second issue is the availability of ARMv8.5A: usually there is about 2 years gap between architecture announcement and SoC release by vendors like Qualcomm or Samsung.  
Let’s hope that new architecture will settle on production soon: presented Memory Tagging Extension will significantly raise memory safety in C/C++.

**References**  
[– Arm A-Profile Architecture Developments 2018: Armv8.5-A](https://community.arm.com/processors/b/blog/posts/arm-a-profile-architecture-2018-developments-armv85a)  
– “Memory Tagging and how it improves C/C++ memory safety”, Kostya Serebryany: [pdf](https://arxiv.org/pdf/1802.09517.pdf) [video](https://www.youtube.com/watch?v=lLEcbXidK2o)  
[– Wikipedia](https://en.wikichip.org/wiki/arm/mte)
