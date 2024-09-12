9/3/2024

# Software Security 

## Buffer Overflow Defense 

### Brain Storming 
- Limit input size 
- Limit the use of programs with user input in root or a admin role 

### Questions 
- Who to defend against BO attacks?
- What are the approaches? 
- What are compile time defenses? 
- What are run time defenses? 
- What is NX bit?
- What is Stack guard?

### Compile Time 
Use a a safe programming language or techniques to harden programs, fending off BO attacks 

### Run Time 
detect and exploit and abort execution at run time 

# Compile Time Defense 

## Safe Languages
Use modern high-level languages that is not vulnerable to buffer overflow attacks 
- compiler enforces range checks 

## Safe Coding Techniques  

Use compilers that warn about linking to unsafe functions

use safer versions of library functions
- gets and strcpy should be getline and strlcpy
- prevents overflow attacks

static analysis of source code to detect unsafe code
- Manual: Code Inspection 
- Automatic: source code scanning tools

## No Range Checking 
Many Functions do not check size of arguments 
- Many C libraries are like this 

### Does Range Checking help? 
Programmer has to supply size variable to work properly 
- when done properly, Range checking does prevent overflow attacks

# Run Time Defense 

## Non-Executable Buffers  
Since buffer overflow uses the buffer to execute malicious code within it, we can prevent code in a buffer from being executed at all. 
- in recent systems executable code within the data section is allowed. 
- this defense is more applicable to stack segment since no legitimate program has code in stack 

NX( No-eXecutable) bit in Page Table Entry
- how a non-executable stack is created and managed within an operating system 

Some applications need executable stack 
- e.g. LISP interpreters

## Address Randomization 

BO and return-to-libc exploits need to know the Virtual address of the destination logic 
- address of the attack code in the buffer 
- address of a standard kernel library routine

same address is used on multiple machines

The idea is to randomize these addresses through arranging the positions of key data areas randomly in a process's address space 


## Array Bound Check 

all reads and writes to arrays will be bound checked at run time 
- is the case of memory safe languages such as Java and .net languages 
- Solves the problem at the cost of performance 

### Libsafe 
dynamically loaded middleware layer library

Intercepts all calls made to known vulnerable library, 

Protects from a pointer and return address from being overwritten 

## PointGuard

Attack: overwrite a function pointer so that it points to attack code 

Idea: encrypt all pointers while in memory 

attacker cannot predict the programs pointer key

## Code Pointer Integrity Check 

during a function call, the return address pointer is changed to the destination of the malicious code. 

If we prevent this then the malicious code is not executed 

This is done by tracking any attempted change in the return address on the stack
- this is more efficient than checking array allocation

## Canaries and StackGuard
Is used to detect and change in the stack due to an overflow by stationing itself between the stack and the return pointer (sfp)

- by checking the canarie's integrity for every function incurs a performance hit 

- has been bypassed by attacks such as Bulba and Kil3r

## Litchfield's Attack 

Microsoft Windows 2003 server implements several defenses against buffer overflow attacks 
- random canary

The attacker targeted the code that is ran when the canary error is called through the exception handler 
- Smashed the canary and overwrites the pointer to exception handler



