
The [CIRT](../../Glossary/CIRT.md) is reviewing an incident that involved a human resources recruiter exfiltrating sensitive company data. The [CIRT](../../Glossary/CIRT.md) found that the recruiter was able to use [HTTP](../../Glossary/HTTP.md) over port 53 to upload documents to a web server. Which of the following security infrastructure devices could have identified and blocked this activity? 

A. [WAF](../../Glossary/WAF.md) utilizing [SSL](../../Glossary/SSL.md) decryption 
B. [NGFW](../../Glossary/NGFW.md) utilizing application inspection 
C. [UTM](../../Glossary/UTM.md) utilizing a threat feed 
D. [SD-WAN](../../Glossary/SD-WAN.md) utilizing [IPSec](../../Glossary/IPSec.md)

> [!faq]- Answer: 
> 
> B 
> 
> Explanation: 
> 
> B. NGFW utilizing application inspectionA Next-Generation Firewall (NGFW) utilizing application inspection could have identified and blocked the use of HTTP over port 53. NGFWs have advanced capabilities that allow them to inspect and identify traffic based on the application layer, not just the port and protocol, enabling them to detect and prevent non-standard use of ports for malicious activities.Therefore, the correct answer is:B. NGFW utilizing application inspection.

