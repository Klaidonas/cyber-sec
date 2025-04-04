
An organization experienced a security breach that allowed an attacker to send fraudulent wire transfers from a hardened PC exclusively to the attacker's bank through remote connections. A security analyst is creating a timeline of events and has found a different PC on the network containing malware. Upon reviewing the command history, the analyst finds the following: 

PS>.\mimikatz.exe "sekurlsa::pth /user:localadmin /domain:corp-domain.com /ntlm:B4B9B02E1F29A3CF193EAB28C8D617D3F327

Which of the following best describes how the attacker gained access to the hardened PC? 

A. The attacker created fileless malware that was hosted by the banking platform. 
B. The attacker performed a pass-the-hash attack using a shared support account. 
C. The attacker utilized living-off-the-land binaries to evade endpoint detection and response software. 
D. The attacker socially engineered the accountant into performing bad transfers.

> [!faq]- Answer: 
> 
> B 
> 
> Explanation: 
> 
> The attacker performed a pass-the-hash attack using a shared support account.

