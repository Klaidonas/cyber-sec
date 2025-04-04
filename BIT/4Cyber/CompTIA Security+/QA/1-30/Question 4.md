
An enterprise is trying to limit outbound DNS traffic originating from its internal network. Outbound DNS requests will only be allowed from one device with the IP address 10.50.10.25. Which of the following firewall ACLs will accomplish this goal? 

A. Access list outbound permit 0.0.0.0/0 0.0.0.0/0 port 53 Access list outbound deny 10.50.10.25/32 0.0.0.0/0 port 53 
B. Access list outbound permit 0.0.0.0/0 10.50.10.25/32 port 53 Access list outbound deny 0.0.0.0/0 0.0.0.0/0 port 53 
C. Access list outbound permit 0.0.0.0/0 0.0.0.0/0 port 53 Access list outbound deny 0.0.0.0/0 10.50.10.25/32 port 53 
D. Access list outbound permit 10.50.10.25/32 0.0.0.0/0 port 53 Access list outbound deny 0.0.0.0/0 0.0.0.0/0 port 53

> [!faq]- Answer: 
> 
> D 
> 
> Explanation: D.
> 
> Access list outbound permit 10.50.10.25/32 0.0.0.0/0 port 53Access list outbound deny 0.0.0.0/0 0.0.0.0/0 port 53Here’s the reasoning:•The first line Access list outbound permit 10.50.10.25/32 0.0.0.0/0 port 53 allows DNS traffic (port 53) from the specific IP address 10.50.10.25 to any destination.•The second line Access list outbound deny 0.0.0.0/0 0.0.0.0/0 port 53 denies DNS traffic (port 53) from any source to any destination, effectively blocking all other outbound DNS traffic.

