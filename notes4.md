## what is concurrency?
- a concurrency is a multiple instruction execution at the same time. it happens in the operating system when there are several threads
  running in parallel

## what is thread?
- Single sequence of process contains independent threads are independently working to complete the work in a single process 
- an independent path of execution in a process 
- Light weight process
- Used to achieve parallelism by dividing a process into independent task that are handled by multiple thread 
- eg: multiple tabs in a browser

## what is thread scheduled?
- threads are scheduled on the basis on the priority whichever comes first will be executed first

## what is thread context switching?
- OS saves the current thread and restores the another thread of same process(Doesn't include memory address space)
- Fast switching compared to process switching
- CPU cache is preserved

## how each thread get access to the CPU
- Each thread has its own program counter
- Depending upon the thread scheduling algorithm, OS schedule these thread


## I/O or thread context switching is done here as well
- We have TCB( Thread control block ) like the PCB for state storage management while performing context switching

## what will be the benefit of Multi-threading
- Responsiveness
- Resource Sharing:Efficient
- Economy: it is more economical to create a context switching threads
    - allocating memory and resource for process creation is costly, so better to divide task into thread of some process
    
- Threads allows utilization multiprocessor architecture efficiently and at a great scale 

- Process Synchronization technique play a key role in maintaining the consistency of shared data
## what is Critical Session?
- the critical session refers to the segment of code where different process  and threads access the shared resource such as common variable etc. Since process execute concurrently any process can be interrupted mid execution

## what is Major thread scheduling issue
- Race condition:
- race condition is a condition where two or more threads are racing to access the same shared data this leads to inconsistent result because they are trying to change it at the same time
- the thread scheduling algorithm is the one that can swap the 
  threads based on the access so it depends on the thread scheduling 

## Solution TO Race condition
- Atomic operation make critical code section an atomic operation
- mutual exclusion
- Semaphores

- peterson solution means using array flag variable with the fixed size of 2
- good for only 2 threads

## what is the disadvantage of mutex/lock
- Locks can be used to implement the mutual exclusion when one process goes in
 the others process cannot enter till the process inside complete fully 

- Disadvantage of it:
- Contention:let the say the first thread that goes into it goes dead so because it is not completing the others have to wait infinitely 
- Deadlock
- Debugging
- High priority task have to starve


## what are the solution to locks disadvantage 
- Condition variable: the condition variable is synchronized primitive 
  thats lets thread wait until a certain condition occurs 
- works with lock
- threads can enter a wait state only when it is acquired a 
  lock when a thread . when a thread enters the wait state it will 
  release the lock and wait until the they send a signal notifying 
  that the other process is completed and then again it acquire 
  the lock state
- why to use conditional variable
- to avoid busy waiting


- Semaphores:Synchronization method used in concurrent programming.they 
  are represented by an integer value that indicate the number of available
  resource or permits

- Binary semaphores include the integer as 0/1 it allows one resource at a time
- Counting semaphores have a variable over by an unrestricted domain having
  control access to a finite number of resource instance

- Multiple threads can execute critical sections concurrently when using semaphores.

- to avoid busy waiting,wait() and signal() semaphores operation can be 
  modified when a process executes wait() and finds the semaphores value is
  not positive it block itself enter a waiting queue associated with a semaphores and switches its state to waiting. control is transferred to the 
  CPU Scheduler which select the another process to execute

- Block process waiting on a semaphores are restarted when another process 
  executes a signal operation . this is achieved through a wakeup operation
  transition the waiting process from the waiting state to the ready state
  placing it in the  ready queue for execution

- Overall, semaphores provide a flexible mechanism for coordinating access to shared resources among multiple program threads while managing contention and avoiding busy waiting.


