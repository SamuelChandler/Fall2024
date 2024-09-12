9/12/2024

# Network Security 

protecting data sent or received over a network 
- data is anything that can be processed by a computer 

2 states of data
- transmission state
- storage state 

Goal is to protect information in both states & on your network infrastructure 
- maintaining availability


## Importance

This is important for the following reasons
- The internet is a public network
- Is built upon TCP/IP
- Stare and Forward Technology

## Attributes of Data that We Protect

- Confidentiality
  - privacy of the information
- Integrity 
  - information has not been modified
- Availability and/or Authenticity 
  - accessability of network services of users 
  - from authentic originator
- non-repudiation
  - Proof that someone has done something 
- Access Control

## Eavesdropping 

common packet sniffers: TCPdump, Wireshark

The act of listening to network traffic 

## Password Pilfering 

Passworkd protection is often the first defense line, which may be the only defense available in the system 

Password Pilfering is the act of taking passwords

## Social Engineering 

Pysical Impersonation
- acting like someone you are not 

Phishing 
- emailing or messaging someone with permissions to steal said permissions
- Can also include dumpster diving 

## Dictionary Attacks 

Steps
1. Obtain information of user names an dthe corresponding hashed passwords
2. Run the hashing routine used by the underlying system on all dictionary words, name, or dates 
3. Attempt to crack the password using this hashing information 

Only hashes of passwords should be stored in a computer system 
- For Linux, passwords are stored in a file under the directory/etc
- For windows, passwords are stored in a file named SAM, which is stored in the system's registry

## Password Sniffing 

Used to capture the keyboard inputs of a user to gain access from the user 

## Identity Spoofing 
attack allow attackers to impersonate a victim without using the victim's passwords

## Man in the Middle Attacks
- Message is modified while in transmission between 2 users
- Usually will intercept, modify, or fabricate the transmitted data between users

## Message replays
- Collect information for a communication, and recreate the communication with valid information using the collected information of the previous information 

## Intrusion
an illegitimate user gains access to someone else's computer systems
- configuration loopholes, protocol flaws, and software side effects
  
Intrusion prevention is a technology for preventing intrusion incidents

IP scans and Port scans a common hacking tools 

## Traffic Analysis

The purpose is to determine whi is talking to whom by analyzing IP packets

## Spam Mail

un-invited emails and messages which are un-welcomed messages

while not intended to bring the use's computer out of service. 

## Broadcast Addressing

Broadcast IP Address
- IP addresses ending with .255

## ICMP - Internet Control Message Protocol

layer 4 protocol 

Carries IP error and control messages

ICMP echo request message is used to test routing between devices

## ICMP 'SMURF' DoS

Broadcast an ICMP echo request message with a spoofed return address to the target device performing a DoS attack from the devices within the network

