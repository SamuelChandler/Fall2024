11/12/2024

# WireGuard

Made by Jason Donenfeld 
- background in exploitation, kernal vulnerabilities, crypto vulnerabilities, and been doing kernel-related development for a long time
- motivated to make a VPN that avoids the problems in both crypto and implementtion that I've found in numerous other projects, 

## What is WireGuard?

Wire Guard is a Later 3 secure network tunnel for IPv4 and IPv6 

Designed for the Linux Kernal 

UDP based, puncheds through firewalls 

Emphasis on simplicity and auditability 

authenticatino model similar to SSH's authenticated_keys.

Replacement for OpenVPN and IPsec

grew out of a stealth rootkit project 

## Security Principles

1: Easity Auditable 
- A low numbers of Lines of Code in each implementation 

2: Simplicity of Interface 
- Wireguard presents a normal network interface
- Everything that ordinarily builds on top of network interfaces - like eth0 or wlan0 - can build on top of wg0
- The interface appears stateless to the system administrator
- If it's not set up correctly, if will refuse to work. failing safe father than running unsafe 

3: Static Fixed Length Headers

4: Static Allocations and Guaded 

5: Stealth 
- Invisible and tries to stay as quiet as possible 

6: Solid Crypto 
- makes use of Noise Protocol Framwork
- The usual list of modern desirable properties you'd want from an authenticated key exchange 
- strong key agreement & authenticity 
- Fast crypto primitives 


## Cryptokey Routing
the findamental concept of any VPN is an association between public keys of peers and the IP addresses that those peers are allowed to use

[A lot can be added from the slides]


## Timers: A stateless Interface for a Stateful  Protocol

[get from slides]

## Performance
- being in kernel space makes it very efficient and performant
- Outperforms all competitors 

