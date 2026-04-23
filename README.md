# SOC Home Lab: Detecting Malicious Process Execution with Sysmon and Splunk

## Project Overview

This home lab demonstrates how to detect malware execution and reverse shell activity using Sysmon and Splunk

The goal was to simulate a real world attack scenario, where a malware establishes a reverse connection and does system processes. Logs were collected using Sysmon and analyzed in Splunk to identify attacker's behavior.

---

## Lab Scenario

1. A malicious file named: Resume.pdf.exe was executed on a Windows machine.

2. The file established a reverse TCP connection to a Kali Linux attacker machine and spawned cmd.exe, which executed system commands.

3. Sysmon captured process creation events and Splunk was used to investigate the attack using process correlation.



## Lab Architecture

Attacker Machine: Kali Linux

Target Machine: Windows 10 Pro

SIEM: Splunk Enterprise

Log Source: Sysmon



## Tools Used

- Sysmon
- Splunk Enterprise
- Kali Linux
- Metasploit Framework
- Python HTTP Server
- VirtualBox
- Windows Event Logs


## Attack Simulation Steps

1. Created a malicious executable using msfvenom
2. Hosted the payload using Python HTTP server
3. Downloaded and executed the file on the Windows machine
4. Established a reverse shell connection
5. Generated system activity
6. Collected logs using Sysmon
7. Investigated logs in Splunk


## Detection Techniques

The following detection methods were used:

- Process creation monitoring
- Parent-child process analysis
- Command execution tracking
- Network connection monitoring


## Splunk Search Example

index=endpoint {bb2dc0da-358f-69ea-960c-000000000300} | table _time,ParentImage,Image,CommandLine



