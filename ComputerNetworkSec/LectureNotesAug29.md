8/29/2024

# TA info 
Zahra Omidi

Zahra.Omidi@utdallas.edu

# Software Security - Buffer Overflow

## Questions for this lecture
- What is a buffer overflow vulnerability
- Why is it dangerous? 
- How can it be exploited? 
- What steps are involved? 
- What are the challenges? 
- What is stack smashing? what is NOP sled ?

## Buffer Overflow 

what? 
- Memory locations beyond the boundary of a buffer are written as part of the buffer

why? 
- Create vulnerabilities that are easy to exploit 
- Used in the first computer worm

how? 
- insert malicious code into the overflow area to take control of a program, and if the program has enough privileges take control of the host's OS (setuid to root)

### Buffer Overflow Vulnerabilities
- behind some of the most dangerous attacks in history 
- 14/20 of the most dangerous attacks that exist are buffer overflow attacks in 2006

### History
- 1988: Morris INternet Worm uses buffer overflow exploit in "fingerd" as of its attack mechanisms.
- 1995: A buffer overflow in NCSA httpd 1.3 was discovered and published on the Bugtraq mailing list by Thomas Lopatic.
- 1996: Aleph One published "Smashing the Stack for Fun and Profit"  in Phrack magazine, giving a step by step fo exploiting stack based buffer overflow vulnerabilities
- 2001: The Code Red worm exploits a buffer overflow in Microsoft IIS 5.0
  
### Goal
Take Control of the program by changing tis control flow to run malicious code

Take control of the host by attacking a privileged program (root shell)

### How the Attack is performed

1. Insert malicious code into main memory by exploiting a buffer overflow vulnerability

2. Transfer control to the malicious code

#### Malicious Code Insertion 

Infect a malicious program to buffer, including overflow area. 

Use existing code with malicious arguments instead of a malicious program. 
- eg a function call to exec (arg)

#### Transfer Control 

change the return address at the end of a function or process so that we can run malicious code.

### Memory Access

What happens when memory outside a buffer is accessed? 

if illegal address(memory doesn't exist)
- bus error? 

memory is protected 
- protection error? 

## Stack Smashing

takes advantage of 
- local variable stored on the stack 
- activation record of the subroutine

Hardest part is to find the address of the first malicious instruction 

### Memory Structure 
- text segment
- data segment 
- heap 
- stack 


## NOP Sled 

NOP (No Operation) is in every processor 

NOP Sled, prepend the malicious code segment with a sequence of machine code for the NOP instruction

increases the chances of getting the malicious code guess correctly by increasing the range of addresses that you need to get correctly. 



