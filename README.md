
<p align="center">
<img src="https://media0.giphy.com/media/v1.Y2lkPTc5MGI3NjExdWszNGw0dDBrMGZnZjBpaGh5bDB4NHoyZmI0Yjl3bGM4dGMxeWU5diZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/8P4bnTyGQykuHxhWOm/giphy.gif", width="300", height="300">
</p>

<h1 align="center">DEDSEC_REDIRMASK</h1>
<h4 align="center">REDIRMASK - Advanced Link Masking Tool for Ethical Hackers & Penetration Testers</h4>

### DESCRIPTION
REDIRMASK is a powerful cybersecurity tool designed for ethical hackers, penetration testers, and security researchers to disguise URLs during authorized security assessments. This advanced tool allows you to mask URLs, making them appear as legitimate links from well-known platforms—essential for social engineering testing, phishing simulations, and red team operations.

### KEY FEATURES FOR SECURITY PROFESSIONALS
- **Social Engineering Testing**: Create convincing masked URLs for authorized phishing simulations
- **Penetration Testing**: Disguise payload delivery links during security assessments
- **Red Team Operations**: Bypass basic URL filters and domain reputation checks
- **Security Awareness**: Demonstrate how malicious links can be disguised in training scenarios
- **Obfuscation Techniques**: Advanced URL manipulation for authorized security research

## Features

Two Masking Modes
  * Custom Masking – Manually set both the masked link and the target link.
  * Template Masking – Select from pre-built link formats like Facebook, Discord, YouTube, and more.

Realistic Link Formats Make your links appear as trusted domains 

Simple & Fast Usage: Just enter your target link and choose a masking method.

### How It Works

Mode 1: Custom Masking
    
    You provide:
    A mask link (the link you want the target to see).
    A target link (the real link where the user will be redirected).

    Example:
    Mask Link: https://google.com/search?q=free-money
    Target Link: https://phishing.com/login

Mode 2: Template Masking

    You provide:
    A target link (the real destination).
    Select a pre-built template (e.g., Facebook, YouTube, Discord).

    Example:
    Target Link: https://phishing.com/login
    Selected Template: Facebook Profile

### INSTALLATION
    git clone https://github.com/0xbitx/DEDSEC_REDIRMASK.git
    cd DEDSEC_REDIRMASK
    python3 -m pip install tabulate 
    chmod +x dedsec_redirmask 
    ./dedsec_redirmask

### TESTED ON FOLLOWING
* Kali Linux 
* Parrot OS 
* Ubuntu

### LEGAL DISCLAIMER
⚠️ **WARNING**: This tool is intended for:
- Authorized penetration testing
- Security research and education
- Ethical hacking with explicit permission
- Red team exercises with proper authorization

**Unauthorized use of this tool for malicious purposes is strictly prohibited and may violate local and international laws. Always ensure you have explicit permission before testing any system or individual. The developers are not responsible for misuse of this software.**

