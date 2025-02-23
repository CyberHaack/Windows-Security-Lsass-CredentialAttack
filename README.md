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
For this project, the following tools were used to demonstrate how attackers exploit **lsass.exe** to retrieve **NTLM hashes**:

1. **VirtualBox**  
   - Used to set up a controlled lab environment for testing.  
   - [Download VirtualBox](https://www.virtualbox.org/wiki/Downloads)  

2. **Windows 10/11 Virtual Machine**  
   - Serves as the target system for extracting NTLM hashes.  

3. **Mimikatz**  
   - Used to extract NTLM hashes from the **lsass.exe** process.  
   - [Download Mimikatz](https://github.com/gentilkiwi/mimikatz)  

4. **Windows Command Line (Command Prompt)**  
   - Used to execute Mimikatz commands and interact with Windows processes.  

5. **Process Explorer (Sysinternals)**  
   - Used to monitor **lsass.exe** and verify its location and behavior.  
   - [Download Process Explorer](https://learn.microsoft.com/en-us/sysinternals/downloads/process-explorer)  


### Optional Tools 
##  **Note**  If you want to proceed further to crack the hashed password, pls do so ethically!!

- **Hashcat:** For cracking retrieved NTLM hashes. [Download Hashcat](https://hashcat.net/hashcat/)  
- **John the Ripper:** For cracking retrieved NTLM hashes. [Download John the Ripper](https://www.openwall.com/john/)  
  

## Steps Taken
This section outlines the steps taken to retrieve **NTLM hashes** from the **lsass.exe** process using **Mimikatz**. Screenshots are included to provide visual guidance for each step.


### Step 1: Set Up the Lab Environment
1. Install **VirtualBox** and set up a Windows 10 virtual machine.
<img width="953" alt="1" src="https://github.com/user-attachments/assets/a8484f0f-b074-42b0-a8a7-f9a2e9eeddef" />

2. Temporarily disable **Windows Defender** to allow **Mimikatz** to run without being blocked:
   - Click on the Start Button > Settings > Update & Security > Windows Security > Click on Virus & Threat Protection > Manage Settings > Toggle the button to turn off Real-Time Protection.
<img width="671" alt="1c" src="https://github.com/user-attachments/assets/f24d035a-7280-4d10-9361-0d9218d1bb8a" />

### Step 2: Download and Prepare Mimikatz
1. Download **Mimikatz** from its GitHub repository (See the link in the Tools Section above).
   
<img width="960" alt="3" src="https://github.com/user-attachments/assets/404c7d7a-089a-4a48-846d-ca17cb5fc7e5" />

![4 - Image of the GitHub Mimikatz file to download](https://github.com/user-attachments/assets/7b21c276-bb89-45ba-8a23-9f74e84f0b2d)
   
2. Extract the files to a folder on the Windows VM.
<img width="862" alt="5" src="https://github.com/user-attachments/assets/3a175558-3b4b-4248-a62c-4979635ea34b" />

### Step 4: Let's Simulate a Normal Login using the login credentials you created when setting up the Windows 10 VM

### Step 5: Navigate to the folder where you extracted Process Explorer and run "procexp64.exe"
<img width="956" alt="13 - Process explorer" src="https://github.com/user-attachments/assets/fa81fd43-4185-4707-a84e-2a11fbd4fb0c" />


### Step 6: Locate lsass.exe in the list of processes, Use the search option ( Ctrl F) to filter the processes. Verify the PID and confirm that it is running from the default location "C:\Windows\System32\Lsass.exe 

<img width="583" alt="14 - Process Explorer" src="https://github.com/user-attachments/assets/ac051764-16f4-4ab6-84bc-4114b9cdf3ce" />

### Step 7: Let's Run Mimikatz to Extract NTLM Hashes
1. Open Command Prompt as Administrator > Navigate to the **Mimikatz** folder and run `mimikatz.exe`:
   
- cd C:\Users\Kachi\Downloads\Mimikatz\x64 (Edit to fit your file Locatio Path)
- mimikatz.exe

Your output should be similar to the output in the screenshot below:

<img width="408" alt="7a" src="https://github.com/user-attachments/assets/8835b702-a2cd-4862-bc69-f0d1c948a8f0" />


### Step 8: Let's Confirm that we have the right privilege by running the prompt below:
- privilege::debug
If this is successful, you should see the Privilege "20" Ok
<img width="304" alt="7b" src="https://github.com/user-attachments/assets/2e9be9de-2b81-4d69-9441-fc2ff2c85a27" />


### Step 9: Let's Use the following command to extract NTLM hash:
- sekurlsa::logonpasswords
<img width="411" alt="8a" src="https://github.com/user-attachments/assets/e9804ae6-054f-4272-ab31-74c1282775c1" />

### After running these Cmdlets, you should have something similar to this screenshot below:
<img width="572" alt="7" src="https://github.com/user-attachments/assets/b4b5d50d-ea11-4179-acea-0a2a7faa232b" />






   
