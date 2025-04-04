
A company's online shopping website became unusable shortly after midnight on January 30, 2023. When a security analyst reviewed the database server, the analyst noticed the following code used for backing up data:
![[Pasted image 20241105085925.png]]
Which of the following should the analyst do next? 

A. Check for recently terminated [DBA](../../Glossary/DBA.md)s. 
B. Review [WAF](../../Glossary/WAF.md) logs for evidence of command injection. 
C. Scan the database server for malware. 
D. Search the web server for ransomware notes.

> [!faq]- Answer: 
> 
> A 
> 
> Explanation: A. Check for recently terminated [DBA](../../Glossary/DBA.md)s.The code indicates that the database was intentionally dropped based on a specific date, which suggests that someone with access and knowledge of the database setup (such as a database administrator) may have executed or scheduled this command. Checking for recently terminated [DBA](../../Glossary/DBA.md)s could help identify if an insider threat or an ex-employee had a role in this incident.