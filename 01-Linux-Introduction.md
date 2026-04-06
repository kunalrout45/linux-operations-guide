-----------------------------------------------------------

Why Linux has so many distributions (History + concept)
Video reference: https://www.youtube.com/watch?v=ShcR4Zfc6Dw

When people say “Linux OS”, they usually mean:
Linux Kernel + GNU tools + utilities = OS

---

###  What Linux Actually Does

- Process management  
- Memory management  
- Device control  
- File system handling  

### Architecture 
Reference Image: https://media.geeksforgeeks.org/wp-content/uploads/20260211170114269757/applications.webp

Think of Linux like a chain of communication:

User → Shell → Utilities → Kernel → Hardware

- **User** → You (or any application) giving commands
- **Shell** → Takes your command and translates it into something the system understands
- **Utilities** → Tools like `ls`, `cp`, `grep` that actually perform the work
- **Kernel** → Core of Linux that talks to hardware and manages everything
- **Hardware** → CPU, memory, disk, etc.

In real systems, most commands you run are utilities, but all actual execution is controlled by the kernel.

### Linux vs Unix

### Objective

Understand the difference between Linux and Unix in the context of real enterprise systems.


## What is Unix?

Unix is a family of proprietary operating systems originally developed in the 1970s. Modern Unix systems are certified and follow strict standards.

 In our environment:
- AIX = a Unix operating system used for core banking systems  
- Highly stable and designed for enterprise workloads  

---

## What is Linux?

Linux is an open-source, Unix-like kernel that forms the base of many operating systems (called distributions).

 In our environment:
- RHEL = a Linux distribution used for application and support systems  
- Flexible, widely used in servers and cloud  

---

## Key Difference 

- Unix (AIX) → Proprietary, tightly controlled, enterprise-focused  
- Linux (RHEL) → Built on open-source, commercially distributed, flexible, widely adopted in industries 

In practical usage, AIX can feel more restrictive compared to Linux because it offers fewer tools and less flexibility for customization.
Linux environments (like RHEL) are more flexible and support a wide range of modern tools, which makes them more suitable for DevOps and cloud-based workflows.
AIX, on the other hand, prioritizes stability and controlled environments, which is why it is commonly used in critical enterprise systems.
For this reason, most of the commands and examples covered in the upcoming modules will be focused on RHEL-based environments, as they are more relevant for day-to-day operations and troubleshooting.
However, many of these core concepts and commands are similar in AIX as well, so the knowledge can be applied across both environments with minor differences.
