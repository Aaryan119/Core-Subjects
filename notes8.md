## what is page fault
- in the physical memory frames. This causes the operating system to fetch the required page from 
  the swap space (secondary storage) and load it into a free memory frame.

- If there are no free frames available when a page fault occurs, the operating system must perform a page replacement.
  It selects one of the currently allocated pages in memory and replaces it with the new page being brought
  in from the swap space.


## what are page replacement algorithm?

- FIFO (First-In-First-Out):
    Allocates frames to pages as they come into memory, replacing the oldest page.
    Easy to implement but performance is not always good.
    Can lead to suboptimal replacements, such as replacing heavily used pages or initialization modules that were loaded long ago.
    Exhibits Belady's anomaly, where increasing the number of frames can lead to an increase in page faults, contrary to other algorithms.

- Optimal Page Replacement:
    Replaces the page that will not be referenced for the longest time in the future.
    Provides the lowest page fault rate among any algorithm.
    Difficult to implement as it requires future knowledge of the reference string, which is impractical.

- Least Recently Used (LRU):

    Replaces the page that has not been used for the longest period.
    Can be implemented using:
    Counters: Associate a time field with each page table entry and replace the page with the smallest time value.
    Stack: Keep a stack of page numbers, with the most recently used page on top and the least recently used page on the bottom. Use a doubly linked list for efficient insertion and removal.

## what is thrashing
- Thrashing is a situation where the system spends most of its time swapping pages between main memory and disk, instead of executing       productive instructions.
-   It occurs when the demand for memory exceeds the available physical memory, leading to excessive paging activity.
    Causes of thrashing:
        Insufficient physical memory
        High degree of multiprogramming
        Memory-intensive processes
    
    Effects of thrashing:
        System spends most time paging
        CPU utilization drops
        Increased response time
        Potential deadlock
    
    Techniques to mitigate or prevent thrashing:
        Increasing physical memory
        Swapping entire processes out to disk
        Page fault frequency control
        Memory compaction


    Thrashing is a severe performance bottleneck and should be avoided or mitigated in operating systems for efficient resource utilization and acceptable system performance.
    