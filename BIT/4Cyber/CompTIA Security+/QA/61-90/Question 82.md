
A security engineer is implementing FDE for all laptops in an organization. Which of the following are the most important for the engineer to consider as part of the planning process? (Choose two.) 

A. Key escrow 
B. [TPM](../../../Glossary/TPM.md) presence 
C. Digital signatures 
D. Data tokenization 
E. Public key management 
F. Certificate authority linking

> [!faq]- Answer: 
> 
> AB
> 
> Explanation:
> 
> A. Key escrow B. TPM presence - **Key escrow:** This is important to ensure that encryption keys can be recovered in case they are lost or forgotten. It is a crucial consideration for Full Disk Encryption (FDE) to maintain access to data even if issues arise with the primary encryption keys.- **TPM presence:** Trusted Platform Module (TPM) is a hardware-based security feature that can store encryption keys securely. Ensuring the presence of TPM on laptops enhances the security of FDE by protecting the encryption keys from being accessed or tampered with.Therefore, the most important considerations for the security engineer are:A. Key escrow B. TPM presence.

