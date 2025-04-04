
A recent penetration test identified that an attacker could flood the MAC address table of network switches. Which of the following would best mitigate this type of attack? 

A. Load balancer 
B. Port security 
C. [IPS](../../Glossary/IPS.md) 
D. [NGFW](../../Glossary/NGFW.md)

> [!faq]- Answer: 
> 
> B 
> 
> Explanation: 
> 
> Port security is a feature on network switches that allows you to limit the number of MAC addresses that can be learned on a specific port. If the limit is exceeded, the switch can take predefined actions such as shutting down the port, restricting traffic, or generating alerts. This effectively prevents attackers from overwhelming the switch with a large number of MAC addresses, which could otherwise cause the switch to behave like a hub, sending traffic to all ports and potentially exposing sensitive data.
