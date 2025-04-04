
A systems administrator receives the following alert from a file integrity monitoring tool: The hash of the cmd.exe file has changed. The systems administrator checks the OS logs and notices that no patches were applied in the last two months. Which of the following most likely occurred? 

A. The end user changed the file permissions. 
B. A cryptographic collision was detected. 
C. A snapshot of the file system was taken. 
D. A rootkit was deployed.

> [!faq]- Answer: 
> 
> D 
> 
> Explanation: 
> 
> D. A rootkit was deployed.A change in the hash of a critical system file like cmd.exe, without any corresponding patches or updates being applied, is a strong indicator of potential malicious activity. A rootkit is a type of malware that can modify system files and hide its presence to maintain persistent and privileged access to a system. If a rootkit has altered cmd.exe, it could be an attempt to replace the legitimate command prompt with a malicious version, or to modify its behavior for nefarious purposes. This is a serious security concern and should be investigated immediately.

