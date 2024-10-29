10/22/2024
# Secure Protocols 

a protocol is a set of rules for exchanging messages between two or more entities over a network

'protocol' in the OSI model is reserved and refers to rules governing communication between a pair of peer entities 

## Definition 
 allows entities achieve the stated aim of the protocol securely
 - adversaries should not be able to defeat the aim of the protocol

## The Principles 
Alice and Bob who wish to authenticate one another or to share a key 

In more complex protocols, trent, a trusted third party might be used

Adversaries:
- Eve, a passive eavesdropper
- Mallory, an active adversary
  - cannot break strong cryptographic mechanisms 

## Cryptographic mechanisms 
used to defend against attacks on network security 

### Entity Authentication 
verifies the origin of recieved data and the claimed identity
- data origin authentication and entity authentication

A data origin authentication mechanism usually be built together with a data integrity mechanism 

typically achieved by exchange of messages using an authentication protocol 

## Definitions 

*Entity authentication*: the corroboration that an entity is the one claimed at a particular point in time 

*Unilateral authentication*: Entity authentication which provides one entity with assurance of the other's identity but not vice versa 

*Mutual Authentication*: [Add from slides]

##  Strong Authentication 
one entity proves its identity to another by demonstrating knowledge of a secret known to be associated with that entity, **without revealing that secret itself during the protocol**
- cryptographic mechanisms are usually used for this 

## Encryption-based Unilateral Authentication

Assume Alive and Bob share a secret key K 

Design goal: Alice to be authenticated 
- Alice sends an initiating message
- Bob sends alice a challenge message R
- Alice responds with {R||B}_K, message R  concatenated with B, encrypted using shared key K 
- Bob checks that the message he received decrypts to give message R||B 
- If it dies, then Alice is authenticated to Bob

### Security of the protocol 
1. who can bob be sure that message 3 in the protocol came from alice 
2. Why can bob be sure that message 3 in the protocol is not a replay of a message from an earlier run of the protocol between himself and alice 

## A Replay Attack 

Suppose Mallory want to impersonate Alice in this protocol
- Mallory cannot prepare the correct reponse to Bob's challange 
- But what if Mallory could predict R? 

Mallory can then pretend to be Bob to get the {R||B}_K and then communicate with Bob using alices token 

## Liveness and Freshness
the replay attack shows that it is vital that the protocol contains a means of checking liveness of principals 

*Liveness*: assurance that message sent by a principal within an acceptably recent timeframe 
- usually ensure via freshness of messages 

*Freshness*: assurance that a message hs not been used previously and originated within an acceptably recent timeframe 

### Methods for providing freshness 
- Nonce (Number used ONCE)
- Time-stamps (clock-based or logical timestamps)

#### Nonces
None property is one time property: nonce should not have been used before 

But many protocols need nonces to be unpredictable to Mallory, rather than simply previously unused 

#### Time Stamps 

Inclusion of date/time in message allows recipient to chick it for freshness 

issue is now that the clocks need to be securely synchronized clocks to prevent replay - non trivial 
- Typical clock drift is 1s per day on work station 

this is the method used by RSA's SecurID token system

##### Logical Time Stamps 

Alternative to clocks: the two parties could use a pair of sequence numbers in thier communication 


## Entity Authentication with MACs

Replace encryption mechanism with a MAC 

1. A --> B:   Message
2. B --> A:   R
3. A --> B:   MAC(R||B)_K 

## Signiture-based Entity Authentication 
instead of challenge/response, now challenge/signature 
- Use nonces or time-tamps for freshness 

### Using Digital Signatures 
[Take From Slides]

### Using Certificates 
[Take From Slides]

## Authenticated Key Establishment (AKE)

entity authentication only achieved for an instant in time typically provided at start of a connection/session 

someone could still hijack the connection after that point 

what if a secure session is needed?

Solution: securely agree session keys as part of the authentication protocol 