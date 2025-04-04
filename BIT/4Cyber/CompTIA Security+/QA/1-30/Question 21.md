
During a security incident, the security operations team identified sustained network traffic from a malicious IP address: 10.1.4.9. A security analyst is creating an inbound firewall rule to block the IP address from accessing the organization’s network. Which of the following fulfills this request? 

A. access-list inbound deny ip source 0.0.0.0/0 destination 10.1.4.9/32 
B. access-list inbound deny ip source 10.1.4.9/32 destination 0.0.0.0/0 
C. access-list inbound permit ip source 10.1.4.9/32 destination 0.0.0.0/0 
D. access-list inbound permit ip source 0.0.0.0/0 destination 10.1.4.9/32

> [!faq]- Answer: 
> 
> B 
> 
> Explanation:
> 
> B. access-list inbound deny ip source 10.1.4.9/32 destination 0.0.0.0/0 This rule specifically denies all inbound traffic from the malicious IP address 10.1.4.9 to any destination within the network. This is the correct way to block the malicious IP address.

