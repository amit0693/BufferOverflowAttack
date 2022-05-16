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

###### 1. General 
![5.](/images/5.png)

###### 2. System/Motherboard
![6.](/images/6.png)

###### 3. System/Processor
![7.](/images/7.png)

###### 4. Display
![8.](/images/8.png)

###### 5. Network
![9.](/images/9.png)

#### Download Ubuntu 20.04 
![10.](/images/9.png)

#### Map Ubuntu 20.04 to VM
![11.](/images/10.png)

#### Details after All-Setting 
![12.](/images/11.png)

#### Starting the VM with Ubuntu 20.04
![13.](/images/12.png)

#### 2. Installation of Ubuntu 20.04 on VM
![1.](/images/13.png)
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

## Section 2.2

### A. Executing the Section 3.4 from Buffer_Overflow_setuid.pdf

I am getting error because of the gcc32 install issue so after seaching on internet i got the solution of installation of gcc-multilib which is used to compile 32 and 64 bit code 
![1.](/images/22.png)



Then able to compile and run make 
both a32.out and a64.out are empty binary files are created
![2.](/images/23.png)



![3.](/images/24.png)


---
