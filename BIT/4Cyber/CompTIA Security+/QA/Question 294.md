
A security analyst is reviewing the logs on an organization's [DNS](../../Glossary/DNS.md) server and notices the following unusual snippet:

![[Pasted image 20241104182413.png]]

Which of the following attack techniques was most likely used? 

A. Determining the organization's [ISP](../../Glossary/ISP.md)-assigned address space 
B. Bypassing the organization's [DNS](../../Glossary/DNS.md) sinkholing 
C. Footprinting the internal network 
D. Attempting to achieve initial access to the [DNS](../../Glossary/DNS.md) server 
E. Exfiltrating data from fshare.int.complia.org

> [!faq]- Answer: 
> 
> C 
> 
> Explanation:
> 
> C. Footprinting the internal network The AXFR request is typically used by attackers to obtain a complete list of DNS records, which can reveal internal IP addresses and hostnames, thereby providing a detailed map of the internal network. This information can then be used for further attacks, such as identifying critical systems or planning network intrusions.

