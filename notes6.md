## what is deadlock
- two or more process are waiting on some resource availability which 
  will be never available as it is also busy with some other process 
  the process are said to deadlock

- in DL,process are never finish executing and the system are tied up 
  preventing others jobs to start

- Example of resource: memory space , CPU Cycles socket i/o devices etc


## how a process utilizes a resource
- Request(if the lock is free and available goes inside the resource)
- use (use the resource till it needed by lock)
- Release(release the lock by termination)


## deadlock detection four necessary condition
1) Mutual exclusion: only one process at a time can use the resource while
    other have to wait to use the resource till it completes it

2) Hold & wait:A process must be holding at least one resource & wait to 
    acquire additional resource till it is free

3) No pre-emption: Resource must be voluntarily released by the process 
    after completion of the process 

4) Circular wait: a set of process are waiting for other process that acquire 
 the resource releasing them P0 is waiting for a resource held by p1 and p1 is waiting for the resource held by p2 and so on a cycle 


## Method for prevention of Deadlock
1) Use a protocol to avoid or prevent for deadlock
2) allow the system to enter the deadlock state, detect it and recover it
3) ostrich algorithm  ignore the problem altogether and pretend that it never 
   happened


4) Deadlock prevention by ensuring that one of the necessary condition
    cannot hold
    1) Mutual exclusion: 
    - use lock for non-sharable resource
    - read only file give them permission for them to be sharable 
    - it cannot prevent it because there are intrinsically 
      some non-sharable resource

    2) Hold & wait: 
    - ensure that when one process request a resource it is not holding any other resource
    - Protocol(A): Require each process to request a process and be 
    allocated all it resources before its execution
    - Protocol(B): Allow a process to request a resource only when it has none
    requesting additional resource after all resource released which they have now

    3) No pre-emption
    - if a process is holding a resource and request another resource 
    that cannot be immediately allocated then preempt all currently allocated
    resources
    - Restart the process only when it can regain its old resource along 
    with the new one 
    - Preempt resource from a waiting process and allocate them to requesting
    process 

    4) Circular wait
    -Impose a proper ordering of resource allocation to prevent this condition.
    -Require processes to request resources in a predefined order,
    ensuring no circular dependency.

## Avoid Deadlock
- what you get :
- no of process
- max need of resource of each process
- currently allocated amount of resource to each process
- max amount of each resource(instance)

- safe state: is the state where is there is no deadlock or circular graph

- unsafe state: is the opposite of safe state

- Uses Banker algorithm to find a safe sequence of resource allocation

- banker algorithm : when a process request set of resources the system must
    determine whether allocating them resources will leave the system in safe state if yes then allocate the resource otherwise wait till other process
    release enough resource


