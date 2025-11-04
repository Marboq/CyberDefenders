# Scenario: 

*In September 2020, your SOC detected suspicious activity from a user device, flagged by unusual SMB protocol usage. Initial analysis indicates a possible compromise of a privileged account and remote access tool usage by an attacker.*

 Your task is to examine network traffic in the provided PCAP files to identify key indicators of compromise (IOCs) and gain insights into the attacker’s methods, persistence tactics, and goals. Construct a timeline to better understand the progression of the attack by addressing the following questions.

 ### Q1: 
 >The attacker’s activity showed extensive SMB protocol usage, indicating a potential pattern of significant data transfer or file access. What is the total number of bytes of the SMB protocol?

### A1: 
>We select the Statistics→Protocol Hierarchy option. And in the image below, you can see in the "Bytes" column how much space each protocol takes up in the transmission.

<img width="1090" height="160" alt="obraz" src="https://github.com/user-attachments/assets/f906d062-435e-47a0-b25f-4a4c3c575473" />

### Flag 1: 4406



### Q2: 
>Authentication through SMB was a critical step in gaining access to the targeted system. Identifying the username used for this authentication will help determine if a privileged account was compromised.
Which username was utilized for authentication via SMB?

### A2:
>After typing the protocol name "ntlmssp" into the filter box, the packets containing this protocol were displayed. Here you can immediately see that in the "Info" column, we see user:Administrator. This is one method. The second method is that by typing "ntlmssp.auth.username" into the filter box, we get only those packets where information about the credentials used in the SMB protocol is visible.

<img width="1090" height="580" alt="obraz" src="https://github.com/user-attachments/assets/5c945ce3-71c5-4f8a-af0f-919f584faa4b" />

### Flag 2: Administrator

















### Q3:
>During the attack, the adversary accessed certain files. Identifying which files were accessed can reveal the attacker's intent. What is the name of the file that was opened by the attacker?

### A3:
>After selecting the File→Export Objects→SMB option, we get a window with the files that were transferred during the captured network traffic. In this case, it is one file that was downloaded – eventlog.

<img width="792" height="576" alt="obraz" src="https://github.com/user-attachments/assets/29d05a02-ef5a-4a18-b8ce-6aa59f520805" />

### Flag 3: eventlog



