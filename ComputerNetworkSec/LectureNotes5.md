9/5/2024

# Malware - Part 1

## Questions

- What is malware and how to classify malwares?
- What is a worm and what is a virus? 

# Malware
A program that is inserted into a system, with the intent of compromising the confidentiality, integrity, or availability of the victim's data, applications, or operating system

## Classifications 

2 Broad Catagories for categorization:
- How it spreads
- the actions and payloads that it performs when the target is reached 

Other Classifications:
- Whether they need a host program. 
- Independent or self contained?
- Does it replicate? 

## Propagation Mechanisms
Infection of existing content by viruses that is subsequently spread to other systems 

Exploit of software vulnerabilities by worms or drive by downloads to allow the malware to replicate

Social engineering attacks that convince users to bypass security 

## Payload Actions
- Corruption of system or data files 
- Encryption of important files (Taking them ransom)
- Theft of service
- Theft of information form the system 
- Stealth, i.e hiding its presence on the system 
- Zombie, to make the target system to act as they want 

## Attack Kits 

At the beginning the development and deployment of malware required considerable technical skill
- Virus Creation toolkits in thee 1990's

Toolkits are often known as "crimeware"

Widely Used toolkits:
- Zeus
- Blackhole
- Sakura
- Pheonix

## Attack Sources 

In recent times attacks are being performed by organizations and groups rather than individuals trying to impress their peers

Sources: 
- Politically motivated attackers
- Criminals
- Organized Crime 
- Organization that sell their services to companies and nations 
- National Government Agencies (The Most Dangerous)

this significantly changed the resources available and motivation behind the rise of malware

## Advanced Persistent Threats - APT's 

Well funded, persistent application of a wide variety of intrusion technologies and malware to selected targets

Typically state sponsored organizations or criminal enterprises

Differ from other types of attack by their careful target selection and stealthy intrusion efforts over extended periods

High profile attacks:
- Aurora
- RSA
- APT1
- *Stuxnet*

# Viruses

A piece of software that infects programs 
- modifies them to include a copy of the virus
- replicates and goes on to infect other content 
- Easily spread through network environments

When attached to an executable program a virus can do anything that the program is permitted to do 
- executes secretly when the host program is run 

Specific to operating system and hardware

## Components

### Infection Mechanisms 
means by which a virus spreads

### Trigger 
Event or condition that determines when the payload is activated or delivered 
- sometimes known as a logic bomb

### Payload
What the virus does 
- involves damages and non trivial activity

## Phases 

### Dormant 
Virus is idle, and will eventually be activated

### Propigation
When the virus self Propigates to other programs 

### Trigger
When the virus's trigger action occurs

### Execution 
When the virus's payload is activated after the trigger 

## Classifications

Classification by Target:
- Boot Sector Infector
- File Infector
- Macro virus
- Multipartite virus

concealment strategy:
- Encrypted virus 
- Stealth virus
- Polymorphic Virus 


## Macro and Scripting virus 

Infect documents that spread through their execution 

Exploit the macro capability of MS Office apps

# AntiVirus Approaches 


Prevention, detection and identification, and removal 

4 Generations of anitvirus software:
- Simple Scanners 
  - Looks for signatures of known viruses
- Heuristic scanners
- Activity traps 
- Full-features protectin

# Worms 

Programs that actively seek out more machines to infect and each infected machine serves as an aurmated launching pad for attacks on other machines 
- Exploits software vulnerabilities in client or server programs 
- Use network connections to spread from system to system
- also Removable media could be used

## Worm Replication 

Methods:
- Electronic mail or instant messaging 
- File Sharing 
- Remote execution capability 
- Remote file access of transfer capability 
- Remo


## Target Discovery 

- Scanning through a random search or hit list 
  - Topological and local subnet scanning is also an option for scanning for targets 

## Slammer (Sapphire) Worm

Jan 24/25, 2003: UDP worm exploiting buffer overflow in Microsoft's SQL Server

Entire Code fits into a single 404 byte UDP packet
- worm binary followed by overflow pointer back to itself 

Classic buffer overflow combined with random scanning: once control is passed to worm code, it randomly generates IP addresses and attempts to send a copy of itself to part 1434

### Impact 

1.25 Billion of damage 

Temporarily knocked out many elements of critical infrastucture 
- bank of america ATM network
- entire cell phone network in south korea 
- 5 root DNS servers 
- continental airlines ticket processing software

The worm did not even have malicious payload

# Worm Detection and Defense 

Worm Propogation Modeling 

Automatic Signature generation 

Detection:
- honeypots