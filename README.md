

## Note:
	1. i haven't finished it yet, i will keep updating :-(
	2. need to change right *Bochs* path in Makefile

## Environment:
	CentOS-6.10-x86_64
	NASM version 2.07
	GCC version 4.4.7
	GNU ld version 2.20.51.0.2-5.48.el6
	Bochs version 2.6.9

## Running:
	$ make run

****
### Timeline:
#### 1. bootloader:
	0. bootloader function:
			enable protection mode
			initialize page table
			probe available memory
	1. $ make run
	2. $ <bochs:1> b 0x1000
	   $ <bochs:2> c  
<div align="center"><img  src="images/bootloader.png" style="zoom:50%" /></div>  
	3. the page table map:
	   $ <bochs:3> info tab  
<div align="center"><img  src="images/bootloader.png" style="zoom:50%" /></div>  
	
#### 2. interruption:
	1. need to alter ./src/kernel/main.c
			call interrupt routine by `int 0x..`  
<div align="center"><img  src="images/bootloader.png" style="zoom:50%" /></div>  
			other interrupt routine such as *timer*  
<div align="center"><img  src="images/bootloader.png" style="zoom:50%" /></div>  

#### 3. memory:
	1. need to alter ./src/kernel/main.c  
<div align="center"><img  src="images/bootloader.png" style="zoom:50%" /></div>  

#### 4. thread schedule:
	1. need to alter ./src/kernel/main.c  
<div align="center"><img  src="images/bootloader.png" style="zoom:50%" /></div>  