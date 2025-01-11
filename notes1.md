## why is os?
- what if there is no OS?
    - if there is no Operating system these thing can happen:
        - they have to write the resource Management and other codes by themselves 
        - so if there is no protection of the memory and space of other process (Resource exploitation)
        - No memory protection (there is no one to isolate so they can change the process happening in other process)

- What is an OS made of?
    - Collection of system software



## what is os?
-   An operating system is a piece of software that manages resources of a 
    computer system  efficiently both environment of hardware and software and 
    provides an environment in which the user can execute the program in efficient manner . 
    it has many function:
    1) it act as interface between hardware and user
    2) hides the underlying complexity of the function(os)
    3) manages the resources efficiently
    4) isolation and memory protection against other process
    5) access to computer hardware 


## Goals of OS?
- Maximum utilization of CPU(we dont want cpu to sit idle)
- No Process Starvation(No process should wait or sit idle)
- High Priority execution(High Priority process should start to have cpu utilization even if other process is working)

## Types Of OS?
- Single Process OS
- Batch Processing OS
- Multiprogramming OS
- Multitasking OS
- Multiprocessing OS
- Distributed OS
- Real Time OS

## What is the Single Process OS?
- Single Process is the process with cpu having one process at a time 
- this leads to No maximum utilization of CPU(because one can have n amount of time taken)
- this leads to Process Starvation of process (because time taken by one leads to another process starvation because of waiting)
- High Priority excution is also not done because of the one process at ready queue will go
- example MSDOS etc

## what is the Batch Process OS?
- firstly user prepare his job using punch card
- Then he submits the job to a computer operator
- the computer operator sort the jobs into batch with similar needs
- then the operator send this batch by batch to process
- All the jobs in one batch execute together
    - Priorities are not done(because it has been done in batches)
    - May lead to starvation(A batch may take more time to complete)
    - CPU may become idle in case of i/o operation of jobs

- example ATLAS etc


## what is the MultiProgramming OS?
- Multiprogramming OS is the CPU having multiple jobs(code and data) in the memory
- this leads to maximum CPU Utilization(because it will never sit idle when one job is in i/o state then other process will take the cpu)
- Context Switching for process(When the CPU switches from one job (process) to another, it saves the current job’s state (context) in a data structure called a Process Control Block (PCB). It then loads the saved state of the next job to continue its execution.)
- CPU idle time reduced 
- example THE etc

## what is Multitasking OS?
- a Logical extension of MultiProcessing OS with a time limit given to every jobs for one cycle 
- because of this more than one task can execute simultaneously
- Context switching and time sharing used
- Increase responsiveness
- CPU idle time further reduced
- Like round robin algo
- example CTSS etc

## what is MultiProcessing OS?
- This is more advance and better then the multitasking OS
- This have the multiple CPU for multiple process
- Better throughPut(means work done per unit time)
- lesser starvation (because there are two cpu for the process if one busy and then take another)
- More reliable because if one CPU fails then choose another
- example WINDOWS etc

## Distributed OS
- A Distributed Operating System (OS) manages a collection of independent, networked computers to function as a single cohesive  system.+
- Multiple Resources: The OS handles multiple computers, each with its own CPU, memory, GPU, etc.
- Loosely Connected Nodes: The computers (nodes) are interconnected but operate independently. They communicate over a network.
- Resource Management: The OS decides how to allocate tasks to different nodes based on their capabilities (e.g., less powerful vs. more powerful resources).
- Distributed Nodes: The nodes are physically separate but work together as if they were a single system.

Example: LOCUS is an example of a distributed operating system.

## Real Time OS
- Real time error free Computation within tight-time boundaries
- example air traffic control, Robots etc.
- example ATCS etc




