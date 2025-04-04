
A company's end users are reporting that they are unable to reach external websites. After reviewing the performance data for the DNS severs, the analyst discovers that the CPU, disk, and memory usage are minimal, but the network interface is flooded with inbound traffic. Network logs show only a small number of DNS queries sent to this server. Which of the following best describes what the security analyst is seeing? 

A. Concurrent session usage 
B. Secure [DNS](../../../Glossary/DNS.md) cryptographic downgrade 
C. On-path resource consumption 
D. Reflected denial of service

> [!faq]- Answer: 
> 
> D 
> 
> Explanation: 
> 
> A reflected denial of service (DoS) attack occurs when an attacker sends forged requests to a server, causing the server to respond to the spoofed IP address (the target) with a large volume of traffic. In the context of DNS, this often involves DNS amplification attacks, where small DNS queries result in large responses being sent to the target. This matches the described symptoms of minimal resource usage on the DNS server but a flood of inbound traffic. The best description of the observed situation, where the DNS server is overwhelmed by inbound traffic with minimal DNS queries, is that it is experiencing a reflected denial of service attack. the correct answer is:D. Reflected denial of service.

