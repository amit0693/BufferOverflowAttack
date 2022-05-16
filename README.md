---
# Buffer Overflow Attack Lab

----

## Section 2.1 

### A. Installation
I am installing VMbox on my owm computer and these are the steps i performed.


### 1. Setup VM

##### Installed from http://www.virtualbox.org/wiki/Downloads
![1.](/images/1.png)

##### Installation begin
![2.](/images/2.png)

##### Installation Finish
![3.](/images/3.png)

##### VM is all setup and need to attach Ubuntu 20.04 ISO file to VM
![4.](/images/4.png)

##### VM Setings - 

###### A. General 
![5.](/images/5.png)

###### B. System/Motherboard
![6.](/images/6.png)

###### C. System/Processor
![7.](/images/7.png)

###### D. Display
![8.](/images/8.png)

###### E. Network
![9.](/images/9.png)

#### 2. Download Ubuntu 20.04 
![10.](/images/10.png)

#### 3. Map Ubuntu 20.04 to VM
![11.](/images/11.png)

#### Details after All-Setting 
![12.](/images/12.png)

#### Starting the VM with Ubuntu 20.04
![13.](/images/13.png)

#### 2. Installation of Ubuntu 20.04 on VM
![2.](/images/14.png)
![3.](/images/15.png)

### B. Other Tasks and Permissions

#### 1. Share folder setup
![1.](/images/16.png)
![2.](/images/17.png)
![3.](/images/20.png)

#### 2. Install updates for Ubuntu 20.04
![1.](/images/19.png)

#### 3. Installation of VirtualBox-Guest
![1.](/images/18.png)

#### 4. Installation of ZSH
![1.](/images/21.png)

---

## Section 2.2

### Executing the Section 3.4 

I am getting error because of the gcc32 install issue so after seaching on internet i got the solution of installation of gcc-multilib which is used to compile 32 and 64 bit code 

![1.](/images/22.png)



Then able to compile and run make 
both a32.out and a64.out are empty binary files are created, after executing the command ./a32.out and ./a64.out able to start session.

These are 32 bit and 64 bit shell code which invokes the execve() system call to execute /bin/sh

Instead of "/sh," the third instruction pushes "//sh" into the stack. This is because "/sh" only has 24 bits and we require a 32-bit number. We can get away with a double slash symbol since "//" is equivalent to "/."

We must use the ebx, ecx, and edx registers to pass three arguments to execve().

The content for these three examples is basically constructed by the majority of the shellcode.

When we set al to 0x0b and run "int 0x80," the system call execve() is invoked.
 
![2.](/images/23.png)

---

### Executing the Section 4 

#### 1. Execution
After provided command for compilation in Buffer_OverFlow_setuid.pdf and set permission to 4755 and owner as root able to compile the code.

Stack.c, which is located in the code folder, is the vulnerable application utilized in this experiment. This program contains a buffer overflow vulnerability, and it's your responsibility to take advantage of it and acquire root access. Because some non-essential information has been deleted from the code described below, it differs slightly from the lab setup file.

A buffer overflow vulnerability exists in the given software. It receives data from a file called badfile and passes it to a buffer in the function bof (). Although the original input can be 517 bytes long, the buffer in bof() is only BUF SIZE bytes long, which is less than 517. Buffer overflow will occur because strcpy() does not check for bounds. Because this is a root-owned Set-UID software, a regular user may be able to obtain a root shell by exploiting the buffer overflow vulnerability.
![3.](/images/24.png)

#### 2. Investigation of Attacks

Execute the command as per PDF
1. touch badfile we created badfile.
2. gdb stack-L1-dbg we Set a break point at function bof() 
3. gdb-peda$ run we Start executing the program
4. gdb-peda$ next we See the note below

![3.](/images/25.png)


#### 3. Launching the attack

As changed the value of start and shell code of the ret and offset i am getting this output 

![3.](/images/26.png)

---
