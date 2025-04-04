
During a penetration test, a flaw in the internal [PKI](../../Glossary/PKI.md) was exploited to gain domain administrator rights using specially crafted certificates. Which of the following remediation tasks should be completed as part of the cleanup phase? 

A. Updating the [CRL](../../Glossary/CRL.md) 
B. Patching the [CA](../../Glossary/CA.md) 
C. Changing passwords 
D. Implementing [SOAR](../../Glossary/SOAR.md)

> [!faq]- Answer: 
> 
> A 
> 
> Explanation: 
> 
> A. Update the CRLThe first priority is to revoke any compromise certificates. This ensures that those certificates can no longer be used for unauthorized access.

