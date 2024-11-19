11/19/2024

# Access Control 

one of the five security services in X.800

## Policies

### Discretionary access control (DAC)
- Cotrols access basedon the identity of the requestor and on access rules stating what requestors are allowedd to do 

### Mandatory access control (MAC)
- Controls access based on comparing security labels with security clearances

### Role based access control (RBAC)
- controls access based on the roles the users have within the system and on rules stating what accesses are allowed to users in given roles 

### Attribute based access control (ABAC)
- Contorls access basedon attributes of the user, te resource to be accessed, and current environmental conditions 

## Subjects, Objects, and Access Rights 

### Subject 
An entity capable of accessing objects
- Owner, Group, World

### Object 
A resource to which access is controlled 
- Entity used to contain and/or recieve information 

### Access right
Describes the way in which a subject may access an object 
- includes: read, write, execute, delete, create, or search 

## Discretionary Access Control 

Scheme in shich an entity may enable another entity to access some resource 

Often provided using an access matrix 
- different permissions based on object and subject combinations 

Each entry in the matrix indicates the access rights of the subject 

## Protection Domains
Set of objects together withaccessrights to those objects 
- more flexable when associating capabilities with protection domains 

In terms of the access matrix, a row defines a protection domain 

## UNIX File Access Control 

files are administered using inodes 
- control structures with key information needed for a particular file
- Several file names may be assiciated with a single inode 
- an active Inode is assiciated with exactly one file 
- File attributes , permissions and control information are sorted in the inode 
- On the disk there is an inode table or inode list that contains the inodes of all the files in the files system 

Directories are structured in a hierarchical tree 
- May contain files and/or other directories 
- Contains file names plus pointers to assiciated inodes 

### Traditional UNIX File Access Control 
Set User ID (SetUID)
Set Group ID (SetGID)
Sticky Bit 

## Users, Roles, and Resources 

Users are the people accessing the service

Role 
- defined by the type of work that this user performs allowing restricions to anything outside of that role 

## Contraints (RBAC)
provide a means of adapting RBAC to the sspecifics of administrative and security policies of an arganization 

A defined relationship among roles or a condition related to roles 

Types: 
- see the slides 

## Attribute Based Access Control 

defines authorizations that express conditions on properties of both the resouce and the subject

Uses the atributes of the Subjects, Objects and Environments it exists in to perform Access Control 


# Identity, Credential, and Access Management (ICAM)

A comprehensive approach to amnaging and implementing digital identities, credentials, and access control 

