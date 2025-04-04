
A security analyst received a tip that sensitive proprietary information was leaked to the public. The analyst is reviewing the [PCAP](../../Glossary/PCAP.md) and notices traffic between an internal server and an external host that includes the following: 

... 12:47:22.327233 PPPoE [ses 0x8122] IP (tos 0x0, ttl 64, id 0, offset 0, flags [DF], proto IPv6 (41), length 331) 10.5.1.1 > 52.165.16.154: IP6 (hlim E3, next-header TCP (6) paylcad length: 271) 2001:67c:2158:a019::ace.53104 > 2001:0:5ef5:79fd:380c:dddd:a601:24fa.13788: Flags [P.], cksum 0xd7ee (correct), seq 97:348, ack 102, win 16444, length 251 ...

Which of the following was most likely used to exfiltrate the data? 

A. Encapsulation 
B. [MAC](../../Glossary/MAC.md) address spoofing 
C. Steganography 
D. Broken encryption 
E. Sniffing via on-path position

> [!faq]- Answer: 
> 
> A 
> 
> Explanation: Encapsulation.
