10/29/2024

# SSL/TLS & SSH 

# SSL/TLS

transport layer Defense 

SSL - Secure Sockets Layer

TLS - Transport Layer Security (RFC 2246)
- TLS1.0 is SSLv3.0 with minor tweaks 

SSL/TLS provides security 'at TCP layer'
- applications need modification 
  - e.g. a thin layer between TCP and application, e.g. HTTP

Widely used for many applications on the Web 

## Basic Features 
used in Web browsers and servers to support 'secure e-commerce' over HTTP

SSl architecture consisted of two layers 
- SSL Record Protocol layer 
- Upper layer
  - aux protocols for communication control 

## SSL Record Protocol
provides secure, reliable channel to upper layer 

Session Concept 
- Defines set of cryptographic parameters to protect a session 
- carries multiple connections to avoid repeated use of expensive handshake protocol

Connection concept
- State defined by nonces, secret keys for MAX and encryption, IVs, sequence numbers
- keys for many connections derived from single master secret created during handshake protocol 

Security services provided 
- Data origin authentication and integrity service (message authentication)
  - MAC using algorithm similar to HMAC
  - Based on MD-5 or SHA-1 hash algorithms 
  - MAC protects 64 bit sequence number for anti-replay
- Confidentiality 

Data from upper layer SSL protocol partitioned into fragments (max size 2^14 bytes)

MAC first then pad (if needed), finally encrypt 

## SSL Handshake Protocol 

Like IPSec, SSL also needs symmetric keys 

**Goals**
- Entity authentication of participating parties 
  - participants are called client and server 
  - Server nearly always authenticated, client more rarely 
  - appropriate for most e-commerce applications 
- Establishment of a fresh, shared secret 
  - shared secret used to derive further keys 
  - For confidentiality and authentication in SSL Record Protocol
- Secure ciphersuite negotiation
  - Encryption an hash algorithms 
  - Authentication and key establishment algo's 

### Key Exchange 
SSl suppoarts several key agreement mechanisms 

The most common is RSA encryption 

[[add more from the slides after lecture]]

### Entity Authentication 

SSL support several different entity authentication mechanisms

Most Common: 
- RSA Based 
- Server authentication criteria: ability to decrypt pre_master_secret and generate correct MAC in finished message using keys derived from pre_master_secret 

### SSL Key Derivation 

Keys used for MAC and encryption in Record Layer derived from pre_master_secret 
- Derive master_secret from pre_master_secret 
[[more in Slides]]

### SSL handshake Protocol - additional features 
session resumption and ciphersuite re-negotiation 

## change to TLS from SSH 
TLS 1.0 <-- SSH 3.0

## Applications 
Secure e-commerce using SSL/TLS 
- no guarantees about what happens to client data after session: may be stored on insecure server - vulnerable to identity theft 

Secure electronic banking 
- client authentication may be enable using client certificates 


# SSH 

Secure Shell 
- Initially designed to replace insecure rsh, telnet utilities 
- Secure remote administratino 
- Extended to support secure file transfer and email

application layer defense 


## SSH 2 Architecture 
SSH Transport Layer Protocol

SSH Authentication Protocol 

SSH Connection Protocol 


## Goals 

Server always authenticated in transport layer protocol 

Client always authenticate in authentication protocol 

Establishment of a fresh shared secret

Secure ciphersuite negotiation 

## Algorithms 

Key establishment through Keffie-Hellman key exchange 

Server authentication via RSA or DSS signatures on nonces 

## v1 vs v2 

Many vulnerabilities have been found in SSH-1 

SSH 1 is still wildly used 

[[Add more on SSH from the Slides after lecture]]


