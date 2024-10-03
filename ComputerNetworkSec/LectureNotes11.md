10/3/2024

# Key Management 

Secret key crypto depends on sender and reciever having a shared key which must be kept secret 

Key agreement or key distribution is the primary problem for this issue 

## Key Management Lifecycle 

### Key Generation
creates the key 

### Key Distribution
distributes the key 

### Key Activation 
key becomes active 

### Key Changes 
key changes its value 

### Final add from slides 
## Key Types

### Session Key: 

Used for one session and is generated dynamically 

### Master Key: 
can be used to encrupt session keys typically shared using key distribution

also known as KEK (Key Encrypting Keys) for when they are used to establish a communication with session keys 

## Distributing Secret Keys

How we distribute keys secretly, without attackers noticing 

### Alternatives 
- Physical Delivery of the key to the other user 
- Using a previously secure session to create a new secure session
- Third party can deliver the key to the other user 
- Third Party can have a secure connection with the two people who want to communicate and transfer keys between them 

### Key Distribution Center (KDC)
A trusted third party is used to communicate with another party through the KDC to establish communication for a temp session 
- different base key for each user to estabish connection with the third party 
- N master keys need to be established between KDC and N hosts.
- Not as costly as having a master key for each communication 

#### Drawbacks 
KDC must not fall to an attack for the system to be secure 

The Nature of the KDC makes it a very large target for attackers 

KDC Has becomes the performance bottleneck for communication 

Communication cannot occur if one party is not able to communicate with KDC 


## Needham-Schroeder Protocol
The Idea of establishing communication with a party with only one of them establishing the connection through a third party KDC 

### Steps:
1. Request for communication with a destination to a KDC from a source entity
2. KDC returns the session key for the destination in the form of a ticket encrypted with the dest and the session key for the source. 
3. Source sends the session key encrypted by the destination master key. 
4. Destination returns Session key for the source to use 
5. Confirming communication 
6. Session established 

### Usage 
is used in the basis of Kerberos, where KDC is called ticket granting server (TGS)

## Diffie-Hellman Key Agreement 

Key Distribution solution that does not use a KDC or a third party.

done without prior agreement on a secre, alice and bob can exchange public numbers
- from these numbers, alice and bob can figure out the same private key
- based on mathematical difficulty of finding the correct key
  

### Steps 
based on a public prime number (p) and public number less than p (g) and for every n in [1,p-1], there is a power k such that n = $g^k$ mod p
1. Sender chooses radom A and sends A' = $g^A$ mod p
2. Reciever Chooses random B and Sends B' = $g^B$ mod p 
3. Alice Computes k = $(B')^A$ mod p
4. Bob Computes k' = $(A')^B$ mod p
5. From Here the session is established 

Shared Secret = k = k' = $g^{AB}$ mod p

only p needs to be prime for this 

### Problems 
Provides no authentication 

Vulnerable to man-in-middle or masquerading attack, where another user is pretending to be one of the two communicating parties  

## Problems with Shared Secret Keys 

- Key Management and Key Distribution 
- Secret Key must be exshanged before communication, or needs the use of a key dist center 
- A host needs a unique key for every host to communicate with -> host nees to hold N-1 Keys 
  - Not feesable with the size of the internet 