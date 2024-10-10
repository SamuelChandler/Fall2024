10/10/2024
# Hashing 

Encryption provides Confidentiality and hashing provides integrity

Ex. 
- SHA-1 
- MD5

## Message Authentication 
a message is authentic when it is unaltered and came from its claimed source 

## Data Integrity

the problem of ensuring that data has not been modifies in transit or while being stored 

Usually done by adding a checksum through parity bits or CRC
- these can be used to prove that data was not altered 
- The issue with this is that the CRC can be recomputed by the attacker to make it valid 

We need a checksum that only the sender can compute 

Message authentication code (MAC) or message integrity code (MIC) is a secret checksum - depends on secret key 

MAC is usually not crc since crc was designed for error detection, not security
- Hashes are the prefered method for security

## Hash Function 
condenses am message M of arbitrary length to a fixed size hash h

$h = H(M)$

Usually a hash function is pyblic and not keyed 

Hash can be used to detect changes to message for **integrity protection** 

### Good Properties 

X can be any length, h(X) is fixed length

Given data X, easy to calculate h(X)

given h(X), computationally infeasible to discover X 
- "one way" property 

Two similar X and Y (different by one bit) results in a very different h(X) and h(Y)

### One Way Function
***fill in later*** 

### One Way Trapdoor Function 
***fill in later***

## Damgard/Merkle Iterative Hash Function 
***fill in later***

## Common Hash Functions 

Ron Rivest created MD and MD2 

Palhp Merkle developed SNEFRU, much faster than MD2

Rivest then made MD3 

***Add More Later***

## MD5 
Input = any length message 
- processed in 512 bit blocks
- processing each block creates an intermediate 128 bit result stored in four 32 bit registers (ABCD)
- Output 128 bit hashed bigest 

## SHA-1 

Standardized for the united states 

Secure Hash Algorithm family of cryptographic hash functions developed by NIST 

- input = any length message to 2^64 bits 
- output - 160 bit digest 

## MAC using Hash function 

MAC needs to include secret key to prevent intruder from altering it and then generate message digest but digest does not have secret key 

***Add more later***

## HMAC 

hash mac

Incorporates secret key into any hash function 

keyed-hash message authentication code 

### Motivations 

Cryptographic hash functions are much faster than encryption 

## other uses for hashes
can be used in place of encryptions
- as is the case of challenge response 
 
