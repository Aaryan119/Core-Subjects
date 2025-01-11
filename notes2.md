## what is Program?
- program is an executable file which contain set of instruction written to complete the specific job or operation on your computer
- its a compiled code.Ready to be executed
- stored in disk

## what is process?
- program is under execution 
- program with double click goes into Ram (ready for execution) default stored in disk

## what is thread?
- a lightweight process 
- single sequence of stream with a process in a single process there are many threads working 
- used to achieve parallelism by dividing a process into subtask independent of execution
- example-multiple tabs opened in a browser

## what is multitasking and multithreading
- difference between both
- more than 1 process being executed using context switched      -more than 1 thread doing work using context switched
- the execution of more than one task simultaneously as          - a process is divided into subtask called as threads 
  called as multitasking                                            which as path of execution

- no. of CPU more than 1                                         - no. of thread more than 1
- isolation and memory protection                                -  no isolation and memory protection

## what are thread scheduling
- threads are scheduled based on their priority. there are process that given time from the OS 
  and then thread are executed by their priority   

## what are thread context switching and process context switching
- OS saves current state of thread & switches       - OS saves current state of process & switches to another process by restoring 
  to another thread of same process                   its state

- doesn't include switching of memory               - include switching of memory address space 
  address space

- Fast Switching                                    - Slow switching

## Components of OS
- kernel
- user space


## what is kernel?
- kernel is the part of the operating system which interacts directly with the underlying hardware and perform the most crucial task
- it is also called the heart of OS component
- very first part of to load from OS when you start the machine


## what is user space
- where application software runs apps don't have privilege to access underlying hardware so thats why they interact with the kernel
- GUI
- CLI

- a shell also known as a command interpreter,is that part where commands come from the user and are being executed. 


## function of kernel?
1) process Management:
- scheduling process and thread on the CPU.
- creating & deleting both user and system process
- suspending and resuming process
- providing mechanism for process synchronization or process communication


2) Memory Management:
- allocating and deallocating memory space as per need
- keeping track of which part of the memory is being used by the process 

3) File Management:
- creating and deleting files
- creating and deleting directories to organize files
- mapping files into secondary space
- backup support onto stable storage media

4) I/O Management:
- to manage and control i/o operation and i/o devices
A. Buffering(data copy between two devices),spooling,caching
1) Spooling:
- within difference speed two jobs
- eg: email spooling and print spooling

2) Buffering
- within one job
- eg: youtube video buffering

3) Caching
- Memory Caching,Web Caching etc


##  how many type of kernel?
- monolithic kernel
- micro kernel
- hybrid kernel

## what is monolithic kernel
- all function are in the kernel itself
- bulky in size
- faster communication(because most of the things are in the kernel)
- less reliable (because every thing in component and if kernel fails everyting will be stopped)
- Memory required to run is high
- eg:  linux , MS-DOS etc

## what is micro kernel
- file management and i/o are been done in user space
- only major function are in the kernel
- More reliable 
- less memory required(compare to  monolithic communication)
- little bit slower compared to monolithic (because if something are in the user space then we switch more to do that things)
- Smaller in size
- eg:L4Linux,Symbian OS etc

## what is Hybrid kernel
- Advantage of both worlds(file management in user space and other thing in kernel)
- combined approach
- speed and design of mono
- modularity and stability of the micro
- eg windows 7+ and macos
- ipc also happen but lesser compared to micro

## how communication is been done between kernel and user space
- inter process communication
- two process executing independently but does sometime needs to communicate for work
- done by shared memory(it is like there are two process p1 and p2 one is in user space and other is in kernel and when to talk both will be talking to shared memory space that has everything from there communication keeps going)
-  message passing( it is nothing same thing but the process are communicating through a joint pipe passing the data and receiving)




