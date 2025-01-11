## how do apps interact with the kernel
- using sci(system call interface) that is in between the user and kernel
- eg mkdir 
- mkdir indirectly calls kernel and asked the file management module to create a new file using create process that create a new directory
- mkdir is just actually a wrapper of actual system calls
- mkdir interacts with kernel using system calls

-eg creating a process
- user executes a process
- get system call from SCI
- system call go through the kernel and kernel execute the process 
- return to user space


- transition from User space to kernel space is done through the software interrupts

- System calls are implemented in C

## what is system call
- System call is a mechanism using which a user program can request a service from the kernel for which it does not have the permission
  to perform 
- user program typically do not have permission to perform operation like accessing I/O devices and communicating other programs

- System calls are the only way through which a process can go into kernel mode from user space


## what are type of system calls
- process control(end,abort,load,execute)
- file Management(create file,delete file,open,close)
- Device Management(read,write,reposition)
- information management(get time,get system data)
- Communication management(Create,Delete Communication Connection)

- example of windows & unix system calls
- process Management(fork(),exit(),wait())
- File Management(open(),read(),write())
- Device Management(ioctl(),read(),write())
- information Management(getpid(),alarm())
- Communication(pipe(),shmget(),mmap())

- pipe() and shmget() are the two ipc process communication function that we do pipe communication and shared memory communication


## what is 32 bit system?
- a 32bit OS has 32bit registers and it can access 2^32 unique memory address i.e. 4GB of physical memory.
  it can process 32 bit of data and  info

## what is 64 bit system?
- a 64bit OS has 64bit registers and it can access 2^64 unique memory address ie 171,179,869,184 physical memory.
  it can process 64 bit of data and info


## what is advantage of 64bit over to 32bit ?
- Addressable Memory- 32bit memory address and 64bit 2^64bit memory address 
- Resource Usage- Installing more RAM on a system with a 32bit OS doesn't impact performance that much but with 64bit OS upgrading ram 
                  will vastly increase your performance
- Performance- All calculation takes place in a register and having the larger register 
              means you can perform larger math operation at the same time
              32bit means 4byte of operation perform in one instruction cycle
              64bit means 8byte of operation perform in one instruction cycle

- Compatibility-  64bit OS can run both 64bit and 32bit architecture whereas the 32bit architecture can only run 32bit architecture only
- Better graphic performance- 8 byte graphic calculation make graphics intensive apps run faster


## what are the different type of Storages?
- Primary Memory-Register,Cache,Main Memory
- Secondary Memory-Electronic Disk,Magnetic Disk,Optical Disk,Magnetic Tapes

## what is Register
- register are the closest to CPU and also the smallest unit of storage(32bit or 64bit)

## what is Cache
- cache is the storage that is second closest to register and stores the repeated things that can come in handy for the cpu to require 
  taken from the main memory
- frequently use to store the instruction temproraily so that cpu can acess it faster


## what is Main Memory
- Main memory is Ram when everything is stored the data from the secondary memory is also stored here


## what is Secondary Memory
- it is a storage media on which computer can store the data and info

## Comparison
- Cost:
- Primary Storage much expensive because of the things they are do really important so to avoid error we make them with best part
- Register are most expensive part of the Whole primary and secondary memory
- Secondary Memory is cheap compared to primary memory eg ssd or hdd compare to RAM


- Access Speed
- Primary speed is very high since it is closed to CPU
- Register has highest speed because of the first after CPU

- Storage Space
- Secondary has more Space because of the Cost


- Volatility
- Primary memory is volatile
- Secondary memory is non-volatile



## what is program?
- program is a set of instruction of code that is ready to execute

## what is process?
- process is program under execution

## how OS creates a process from Program
- Load the program and static data(used for initialisation) into memory
- Allocate Runtime State- part of memory that store local variable,function argument and return values
- Allocate the heap Memory- part of memory to use for dynamic allocation 
- I/O related task- i/p handle and o/p handle and error handle
- OS handoff the task to main()
- Process is stored in Memory


## Architecture of OS
- Assets
- Data-(global and static data)
- Text-(compiled code(Loaded from the disk))

## what are the feature of OS?
- Feature that allow identifying a process uniquely 
- Process table :
- All process are tracked by OS using a table like data structure
- each entry in table is a PCB 

- PCB:
- Data structure used for each process . PCB stores the info for the PCB such as process id,program counte,process state ,priority etc
- Assets


## what is PCB each layer functionality?
- process id-unique identifier
- Program Counter- next instruction address of the program 
- Process State- Stores process State
- Priority- based on priority a process get cpu time
- Registers- when the process is running and its time slice expires then it goes again to state of waiting then the current state of it 
            is stored in the register and when the time comes to start it again the PCB takes the info from the register the current state of process


## what are the Process States?
- New: OS is about to pick the program and then convert it into the process
- Run: Instruction are being executed;CPU is allocated
- Waiting: Waiting for I/O
- Ready: the Process in Memory,waiting to be assigned a processor
- Terminated: the process is finished execution PCB entry removed from process table

## what is process Queues?
- job queue:
- process is new state
- present in secondary memory
- Job scheduler- take the process from a pool of process and put it in the ready queue

- Ready queue:
- CPU scheduler- pick the process from ready queue and send it to running queue


## what is degree of multiprogramming
- the no of process in the programming
- LTS control degree of multiprogramming

## what is dispatch
- the module of os that give control to cpu given to the process selected by STS


## what is mid term scheduler
- midterm scheduler are the ones that manages the process sending from ready to running 
- this is done because of the degree of multiprogramming increase in the cpu
- to free the memory mid term scheduler put first which can be done process that can be completed in the memory limit
- and then take one by one process to execute so that memory do not run out
- swapping is the process name:  it is a mechanism in which a process is swapped temporarily out of the main memory to secondary disk 
  and make the memory available to other process at some time later the system swap back the process from the secondary storage to main memory

## what is context switching?
- Switching the CPU to another process require performing a state save of the current process and a state restore of a different process
- when this occurs the kernel saves the context  of the process in the pcb and load the saved process and restore and load it to cpu

## what is orphan process
- orphan process is a process where the process parent process is terminated and the child process it is still running
- then the kernel put the child process to init (the first process of OS)

## what is the Zombie process
- a zombie process is the process where the child process is terminated and the process still remain in the process table
- this happens because of the parent process call the child exit status but receive it after the child is already terminated 
- so that why till the exit status reaches the child process remain a zombie process 


## what is process Scheduling
- Basis of multiprogramming-OS
- By switching the CPU among processes the OS can make the computer more productive
- Many process are kept in memory at a time,When a process must wait or time quantum expires the OS taken the CPU away from that process and
  give the CPU another pattern continues

## what is CPU scheduler?
- whenever the process become ideal,OS must select one process from the ready queue to be executed
- Done by STS

## what is Non-preemptive Scheduling
- Once cpu has allocated a process then process will not go back until it is completed and get terminated or goes in wait state by itself
- As a result the another process starve by waiting 
- Low CPU utilization


## what is Preemptive Scheduling
- CPU is taken away from the from a process after a time quantum expires or after the set timer along with terminating 
  or switching to wait state
- Less Starvation
- High CPU utilization

## what is Goals of CPU scheduling?
- Maximum CPU utilization
- Minimum TurnAroundTime(TAT)(Completion Time-Arrival Time)
- Minimum Wait-Time(TurnAroundTime-BurstTime)
- Minimum Response Time(time duration between the process getting into ready queue to allocate the CPU for the fist time)
- Max Throughput of System(throughput is a no of process completed per unit time)

- Arrival time(AT): time when process arrived at the ready queue
- Burst Time(BT):time taken by the process to get executed
- Completion Time(CT):time taken by the process to get terminated


## what is FCFS algorithm
- whichever process comes first in the ready queue will be given priority 
- there is no dependency on the BT or something 
- it will lead to process starvation because if some process have a bigger BT then other and it is arrival time is first then it will get   priority


## what is convoy Effect
- convoy effect is a situation where the other process starve because of the priority based on the arrival time
- it is done when the one process take the resource for longer time and other cannot use it because the process is taking longer
- this cause  poor resource management 


## what is SJF(non-preemptive version)
- it takes the shortest burst time first means the priority set to the shortest burst time will get the chance first
- it is best algorithm but it is not implementable because it is choosing from all the process and this is not possible because process come 
  one by one not all together
- this will have convoy effect(as the first arrival will be taken first after that burst time will be considered and if the first process have very high burst then other process will starve)
- this may lead to starvation

- SJF (pre-emptive version):
- less starvation 
- No convoy effect


## what is priority Scheduling(Non pre-emptive version)
- based on the priority (priority is assigned to process when they are created)
- SJF is the special case of general priority scheduling

- Priority Scheduling(Pre-emptive version)
- Current Run state job will be pre-empted if next job has higher priority than the back process
- May cause indefinite waiting(Starvation) for the process having less priority(true for both the non-preemptive and pre-emptive) version

- Ageing is the Solution
- Gradually increases the priority of the process that waited so long(eg: increase the priority by 1 after every 15 minutes)

## what is Round-Robin Algo
- Most Popular
- Like FCFS but preemptive
- Designed for time sharing system
- Criteria: At+time quantum(TQ), hence very low starvation
- Easy to implement
- if TQ is small more context switch(more overhead)

# what is multi-level queue Scheduling
- System process: created by OS
- interactive process: user input required(foreground)
- batch process:*no i/p (background)

- highest priority to low priority
- first and second are the Round Robin algo 
- third one is FCFS algo
- and between these three there is a priority scheduling pre-emptive version


- this is average waiting time is More because of priority scheduling one process with the highest will get all the resource will other 
  will not get the chance so they will starve(convoy effect)


## what is multi-level feedback queue
- multiple sublevel queue
- inter queue movement is allowed means it will divide them based on burst time
- BT increases then shift that process to lower queue
- I/O bound and interactive process 
- Ageing method is the solution
- Flexible 
- configurable OS design

- [tq-2]-
- [tq-4]-
- [tq-8]-
- [fcfc]

- this is the example of the multi level feedback queue

- Design of MLFQ 
- No of queues
- Scheduling Algo in each queue
- Method to upgrade a process to a higher queue
