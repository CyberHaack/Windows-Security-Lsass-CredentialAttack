# Windows Security Lab - Lsass Credential Attack Simulation 


## Objective
The primary objective of this project is to demonstrate how attackers can exploit the **Local Security Authority Subsystem Service (lsass.exe)** in Windows to retrieve **NTLM hashes**. Using tools like **Mimikatz**, this project simulates the process of extracting hashes from memory, highlighting the risks associated with unprotected lsass.exe processes and the importance of securing sensitive credentials.


## Skills Gained
- **Understanding lsass.exe:** Learn its role in Windows authentication and how attackers target it.
- **Hands-On Experience with Mimikatz:** Retrieve and analyze NTLM hashes from memory.
- **Windows Security Concepts:** Explore how Windows manages credentials and the importance of protecting lsass.exe.
- **Ethical Hacking Foundations:** Develop foundational skills in ethical hacking and penetration testing.
- **Tool Proficiency:** Gain familiarity with Mimikatz and command-line tools for interacting with Windows processes.


## Tools Used
This project utilizes the following tools to demonstrate how attackers exploit **lsass.exe** to retrieve **NTLM hashes**:

1. **Mimikatz**  
   - Used to extract NTLM hashes from the **lsass.exe** process.  
   - [Download Mimikatz](https://github.com/gentilkiwi/mimikatz)  

2. **Windows Command Line**  
   - Used to execute Mimikatz commands and interact with Windows processes.  

3. **Process Explorer (Sysinternals)**  
   - Used to monitor **lsass.exe** and verify its location and behavior.  
   - [Download Process Explorer](https://learn.microsoft.com/en-us/sysinternals/downloads/process-explorer)  

4. **VirtualBox**  
   - Used to set up a controlled lab environment for testing.  
   - [Download VirtualBox](https://www.virtualbox.org/wiki/Downloads)  

5. **Windows 10/11 Virtual Machine**  
   - Serves as the target system for extracting NTLM hashes.  

### Optional Tools (for Further Exploration)
- **Hashcat:** For cracking retrieved NTLM hashes. [Download Hashcat](https://hashcat.net/hashcat/)  
- **John the Ripper:** For cracking retrieved NTLM hashes. [Download John the Ripper](https://www.openwall.com/john/)  
  
