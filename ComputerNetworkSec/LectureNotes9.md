9/26/2024

# Secret Key Cryptography

topics:
- diffusion/confusion
- Feistel cipher
- DES
- Breaking DES
- brute force Attack 

# Diffusion/Confusion

done to create ciphers that are strong against statistical analysis

## Claude Shannon 
- Caused the creation of the new field of information theory 
- built the foundations of digital circuit design 
- proposed 2 concepts: Diffusion and Confusion

## Diffusion 

Statistical characteristics of plaintext is hidden by having each plaintext letter effect the encoding of many ciphertext letters

makes it difficult to perform frequency analysis

can be accomplished by repeatedly transposing the data, followed by a function by a function on that transposition 

good diffusion if a change in a plaintext bit will change each siphertest bit with probability 0.5 

## Confusion 

relation between statistics of **ciphertext** and **key** is very complex 

is ahieved by a complex **substitution** algorithm

## Product cipher

a block cipher consisting of a sequence of simple operations (subsitiution,permutation, modular arithmetic)

- individual operations are not secure, but a long chain of such operations will create sufficient confusion and diffusion
- 
when using only substitution-permutation network 

# Fiestel Cipher 

1970 Horst Feistel and colleagues created a proposed cipher

consists of multiple rounds:
- Substitution
- *get from slides*
- *get from slides*

in 1971 IBm connercialized and sold a Feistel cipher. 
- n= 16 rounds, 128-bit blocks, 128-bit keys

# DES (Data Encryption Standard)

approved as a standard in 1977 
- replaced by AES in 2001

64 bit 0's -> key(password) -> random 12 bit salt -> (repeat 25 times)

- done 25 times to make brute force attacks take longer and prevent attacks due to time waste. 

- compared the result and the current value at the end of the hash. Succeeds if they are the same

# F-Function

Steps:
- Expand half block from 32 to 48 bit 
- XOR with subkey
- takes each 6 bit and doing nonlinear transform to 4 bit according to lookup table 
- P-box does fices premuption for the sake of getting it to be 32 bit 


# Brute Force Attack 

Attacking using every permutation of a possible input to get the correct hash 
- will try to entire key space 

# differential cryptanalysis
statistical analysis of cipher based on way particular bits change or do not change when bits in plaintexts are flipped 
