9/10/2024

# Malwares - Part 2 

Questions:
- What are known malwart ytpes
- What is a bot, and what is a botnet?
- What is the cycle of a botnet 
- What are the characteristics of a botnet 


# Botnets
a network of autonomous programs that can be activated remotely to do what a botmaster wants them to do. 
- often refered to as zombies and zombie master
- Controlled and upgraded from command and control servers

Used as a platrorm to mount various types of attacks 
- spam & click fraud


# History
- 1993: early IRC bot, "Eggdrop"
- DDoS bots (late 90s)
- RAT (Remote Administration Trojans) (late 90s)
- IRC bots (mid 2000s)

## IRC Based command and control

Agobot, sdbot spybot, GT-bot

Extensible and customizable codebase
- hybrid of bots, rootkits, trogans, worms 

Actively evade detection and analysis
- code obfuscation 
- detect debuggers, VMware, disassembly 
- Point DNS for anti0virus updates to localhosts 

# Lifecycle 
- Exploit a vulnerability to execute a short program (shell code) on victim's machine
  - Buffer overflows, email viruses
- Shellcode downloads and installs the actual bot 
- Bot disables firewall and antivirus software
- Bot locates IRC server, connects, joins channel
  - typically need DNS t find out server's IP address
  - Authentication procedures included
- Botmaster issues authenticated commands 

# IRC-based Botnet Lifecycle 
- Exploit 
- Bot Download
- DNS lookup for the IRC server 
- Join Botnet 
- Commands from botnet/botmaster from the IRC server

# Detecting Botnet Activity

- alot of DNS queries for IRC servers and IRC activity when the botnet is active or a device is infected 
- DNS used by zombies to find the maste, and by the master to find if a zombie has been blacklisted

IRC and DNS activity is a very visible in the network 
- look for hosts perfoming scans and for IRX channels with a high percentage of such hosts 
- look for host who ask many DNS queries but recieve few queries about themselves

Easily evaded by using encryption and P2P (Peer to Peer)

# Rise of Botnets 
 2003: 800 - 900,000 infeced hosts, up to 100K nodes per botnet 
 2006: 5 million distinct bots, but smaller botnets 

 For-profit criminal activity 
 - spread spam 
 - Extort Money by threating and unleashing DoS attacks 

Now Using P2P instead of IRC 

# Botnet Stages

Complimentary mechanisms also exist at each step 

1. Conception 
2. Recruitment
   1. Collect hosts for the botnet increasing its power 
3. Interaction 
4. Marketing 
   1. Needed To make money using the services provided by the botnet 
5. Attack Execution 
6. Attack Success 

# Characteristics

- Conception 
  - Motivation 
  - Design 
  - Implementation
- Recruitment 
- Interaction 
  - Internl 
  - External 
- Marketing 
- Arrack Execution 
  - DDoS
  - Spam 
  - Phishing 
  - Click Fraud 
- Complementary Hiding Mechanisms 
  - Ciphering 
  - Binary Obfuscation 
  - Polymorphism
  - IP Spoofing 
  - Email spoofing 
  - Fast-flux

# Botnet Interaction 

Internal 
- Registration 
  - static 
  - Dynamic
- C&C 
  - Types of Messages: Orders or control
  - Direction of the information: Push or Pull 
  - Communication Protocols: IRC, HTTP, P2P

External 
- DNS 


# Botnet-based Attacks

- Spam 
- Phishing 
- DDoS

# DoS
Goal
- Overwhelm victim machine or network and deny service to its legitimate clients 

Only From One Source

Often Exploits networking protocols 
- Smurf: ICMP echo request to broadcast address with spoofed victim's address as source 
- SYN flood: send logs of "open TCP connection" requests witb spoofed source addresses
- UDP flood: exhuast resource by sending thousands of bogus UDP messages 

# DDoS
- Built a botnet of zombies 
- Command zombies to stage a coordinated attack on the victim 
  - No need to spoof source IP addresses of attack packets 
  - Even in the case of SYN flood, SYN cookies don't help
  
  ## Architecture 

  1. Attacker commands Master Machines 
  2. Masters command zombie machines 
  3. Victim get attacks by zombie machines

