<img width="1920" height="386" alt="image" src="https://github.com/user-attachments/assets/645d473a-76b5-451f-8d90-8ef800060ac6" />


### Assigned 
- cr4cx

### case study
The email was classified as phishing post-delivery after an automated analysis. If the email is spoofed or contains any suspicious links or files, it must be deeply investigated.

**flags**
- attachment files - REPORT.rar (very unlikely)
- failed security checks - SPF, DKIM

**comment**
- who    : microsoft Support<support@microsoft.com>
- what   : classified as phishing post-delivery after an automated analysis
- when  : mar 27th 2025 at 19:25
- where : Eddie Huffman, IT Manager<e.huffman@tryhackme.thm>
- why      : The email contained attachment named REPORT.rar, failed the security checks: SPF/Fail; DKIM/Fail and email uses urgency/social-engineering language.

**verdict**
- True Positive.
