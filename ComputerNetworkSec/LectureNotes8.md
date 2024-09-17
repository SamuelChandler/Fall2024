9/17

# Cryptography - Overview

concepts to cover:
- confidentiality 
- encryption/decryption
- public and private keys
- cryptanalysis/cryptanalyist


## Terms 

**Encryption**: process of encoding a messange from sender to recipient or information that is stored in a computer so that its meaning is not understandable to others

**Decryption**: reversing the process of encryption 

**Encrypted information**: protect message confidentiality 

**Cryptography**: the practice an study of secret writing **cryptos**:secret hidden messages

**Stream Cipher**: *one plaintext symbol* is encoded immediately into one ciphertext symbol.

**Block cipher**: *group of plaintext symbols* is encoded into group (block) of ciphertext.
- usually better but slower
- Most applications use block ciphers

## Symmetric key cipher:

when encryption and decryption use the same key for the encoded information 

- secret key is known only to sender and receiver 

- depends on the secrecy of the key not the algo 

- biggest weakness is the sharing of the key and securing the sharing of that key for the security channel to occur. 

## Public Key Encryption or Asymmetric Key Cipher

We Use a public key that encrypts the information and is then decrypted by the receiver 
- the public key does not need to be protected in this case 
- only the secret key at the receiver needs to be protected 

public key is always sent to the sender of the content by the recipient oof the content 


## Steganogrphy

cryptography refers to messages with hidden meaning 

steganography refers to hidden messages 

- ex. Hiding information in image files or audio files 

steganalysis: detection of hidden messages 

## Security though Obscurity 

Controversial principle that attempts to use secrecy for security 


## Unbreakable vs Computationally Difficult

2nd Kerckhoffs' principle: cryptosystem should be practically indecipherable, if not mathematically indecipherable

## Cryptanalysis

trying to recover key, plaintext, or both 

cryptography (defense) and cryptanalysis (offense) have co-evolved 


### Mono alphabetic substitution cipher 

map each letter to another letter 

dependence of the base structure and order of the alphabet was the main weakness of the attack 

- can be cracked using the frequency of the characters used compared to the base frequency of the attackers. as well as commonly used words 




