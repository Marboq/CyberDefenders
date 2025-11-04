# Scenario: 

*In September 2020, your SOC detected suspicious activity from a user device, flagged by unusual SMB protocol usage. Initial analysis indicates a possible compromise of a privileged account and remote access tool usage by an attacker.*

 Your task is to examine network traffic in the provided PCAP files to identify key indicators of compromise (IOCs) and gain insights into the attacker’s methods, persistence tactics, and goals. Construct a timeline to better understand the progression of the attack by addressing the following questions.

 ### Q1: 
 >The attacker’s activity showed extensive SMB protocol usage, indicating a potential pattern of significant data transfer or file access. What is the total number of bytes of the SMB protocol?

### A: 
>We select the Statistics→Protocol Hierarchy option. And in the image below, you can see in the "Bytes" column how much space each protocol takes up in the transmission.

<img width="1090" height="160" alt="obraz" src="https://github.com/user-attachments/assets/f906d062-435e-47a0-b25f-4a4c3c575473" />

