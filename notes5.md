## What is consumer and producer problem?
- Producer is the one that produces the data
- Consumer is the one that consumes the data


- Critical Section(Buffer):shared resource

- I don't want inconsistency in data i want synchronization in data

- Sync b/w producer and consumer

- Producer must not insert data when the buffer is full
- Consumer must not consume data when the buffer is empty


- Solution:

1) Mutex- Binary Semaphores acquire lock buffer
2) Empty- counting Semaphores initial value should be n
    - tracks empty slots
3) full- tracks filled slots
    -initial:0

## what is Reader and Writer Problem?
- Reader thread->read
- Writer thread->write Update 

- if >1 Reader are reading
- if write >1 writer are writing or updating and some other thread (R/W) 
  in parallel

- that means race condition can occur and this leads to data inconsistent


- Solution for the problem include three variable :
1) mutex/lock: it is used to give control using lock to control the read count variable ensure it is updated safely
2) the semaphores: it is used to control the section for the accessing the resource by who goes first whom access should be given. it allows only one 
writer at a time
3) readCount: tracks the number of reader currently accessing the resource


## what is Dining Philosopher problem?
- dining philosopher problem is when there is dining table circular
  having 5 forks and 5 people and 5 noodles
  each want two works simultaneously to eat the noodles and complete it
  but because of the people acquired the one fork on their left each
  now no fork is left so they are struck forever because no one will get 
  that no one is ready to leave one so it is a deadlock

- solution to this problem:
1) Odd-Even Solution: Philosophers are divided into two groups based on their position (odd or even). Odd-positioned philosophers pick up their left fork first, while even-positioned philosophers pick up their right fork first. This breaks the symmetry and prevents circular deadlock scenarios.

2) N-1 Fork Selection: Only one philosopher is allowed to pick up all the forks except for one. This philosopher acts as a referee, ensuring that deadlock cannot occur. The remaining philosopher can then pick up the last fork, eat, and release the forks. This solution introduces a central authority to control resource allocation, preventing deadlock.


