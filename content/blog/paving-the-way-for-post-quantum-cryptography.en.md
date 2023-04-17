+++
lang="en-GB"
title="Paving the way for Post-Quantum Cryptography"
date="2022-09-05"
author="Eugene Wypior"
image="/blog/PostQuantumCrypto-3.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

Two months ago, in early July, the US National Institute of Science and Technology (NIST) announced that the results of a six-year competition amongst the set of post-quantum algorithms had resulted in the selection of four initial algorithms (with the view of eight in total). These encryption tools are designed to withstand the assault of a future quantum computer which could potentially crack the security used to protect privacy in the digital systems we rely on every day such as online banking and email software. The four selected encryption algorithms will become part of NIST’s post-quantum cryptographic standard expected to be finalised in about two years.

The algorithms are designed for two main tasks for which encryption is typically used – general encryption which is used to protect the information exchanged across the public network, and digital signatures used for identity authentication.

To provide for general encryption, it was agreed to use the CRYSTAL-Kyber algorithm. The reason this algorithm was chosen is that it uses small encryption keys that two parties will be able to exchange easily as well as the fact that it provides an excellent speed of operation.

For the digital signatures, the collective headed by NIST selected three algorithms – the CRYSTAL-Dilithium, FALCON, and SPHINCS+. The first two scored highly in efficiency in reviews and NIST recommendation is to primarily use the CRYSTAL-Dilithium algorithm with FALCON for applications that need smaller signatures than CRYSTAL-Dilithium can provide. The SPHINCS+ algorithm is reportedly somewhat larger and slower than the first two, but it is valuable to have as a backup as it is based on entirely different math than all the other NIST selections.

The first three algorithms are based on a family of math problems known as structured lattices, whereas the Sphinx algorithm uses hash functions. The outstanding four algorithms still under consideration, which are to be used for general encryption, will not be based either on lattice math or hash in their approaches. The idea here is to advance a pool of varied solutions, which once deployed will be selectable and easy to switch over shall the need arise.

While the standard is in development, NIST encourages security experts to explore the new algorithms and consider how their applications will use them, but not to bake them into their systems yet, as the algorithms could change slightly before the standard is finalised.

Nobody knows nowadays if or when quantum computers will come into existence. The new generation algorithms are fast enough for there be no reason not to transition to them in the foreseeable future as soon as we know we can trust them.