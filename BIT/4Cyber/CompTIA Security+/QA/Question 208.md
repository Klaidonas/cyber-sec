
A security analyst is investigating an application server and discovers that software on the server is behaving abnormally. The software normally runs batch jobs locally and does not generate traffic, but the process is now generating outbound traffic over random high ports. Which of the following vulnerabilities has likely been exploited in this software? 

A. Memory injection 
B. Race condition 
C. Side loading 
D. SQL injection

> [!faq]- Answer: 
> 
> A 
> 
> Explanation: 
> 
> A is correct.Memory injection allows the attackers to inject malicious code directly into the memory of a running process which can then be used to execute arbitrary commands or generate unauthorized network traffic. Race Condition refers to two processes competing to modify the same resource which can lead to unpredictable behavior but is less likely to cause abnormal outbound traffic. Side Loading refers to loading a malicious DLL into a legitimate process. SQL injection involves injecting malicious SQL code into a database and is primarily concerned with database manipulation rather than generating outbound network traffic.
