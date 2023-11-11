# Intuiting Latency and Throughput
notes from video: https://www.youtube.com/watch?v=CEkBsyN1j_Q

We already INTUITIVELY knows about LATENCY and THROUGHPUT in our REALWORLD 

We can get this intuition very easily with a Laundry example: 
    Split machine: 2 machines, each does 1 work:  (1 Washing, 1 Drying)
    vs
    Combo machine: 1 machines, does both works: (Washing then Drying)
    -> The 2 machine is faster when have a lot of clothes to wash

    Load: 1 luot giat do 
    Each load need 2 process: 
        + Wash 
        + Dry 
    total amount of load: n
    Know that each process takes 1 hour 

    -> 1 machine takes 2n hour 
    -> 2 machine takes n+1 hour

    the 2 machines is FASTER because there are OVERLAPPING between loads 
        -> in EACH HOUR can do 2 PROCESS: dry and wash (2 different load)

-> Use this example to understand LATENCY and THROUGHPUT:  

LATENCY:  
    -> the idea that MEASURE HOW LONG it takes a particular LOAD to be DONE 
        -> How long did it take 1 job to be done 
        -> in the term of LATENCY: 
            1 machine 2 jobs  
            2 machines each 1 job
            -> are the SAME 

    Definition: Latency is the total time for one operation to complete, from start to finish.
    Laundry Example: Using the analogy, it's the time it takes for a load to go from the washer to the dryer.

    -> Hours per Operation 

THROUGHPUT:  
    -> HOW MANY of these load can i put in these machines every unit of time (hour) at full capacity  ? 
        -> 2 machines each 1 job -> 1 load per hour 
            -> every hour we put 1 new load in 

        -> 1 machines 2 jobs -> .5 load per hour (2 hour per load)

    Definition: Throughput is the rate at which operations are completed when the system is at full capacity.
    Laundry Example: It's the number of loads completed or started per unit time.

    -> Operations (at MAX CAP) per Hour 

NOTE: these 2 sounds like they inverse each other 
    but actually the value of them are not the same
    LATENCY input is 1 operation (just 1 task, NOT FULL CAP)
    THROUGHPUT input is how many tasks at FULL CAP

DEPENDENCY CHAINS:
    Definition: 
        -> Explains that some operations depend on others, forming dependency chains.

    Laundry Example: 
        -> Shows how dependency chains affect the overall efficiency of the laundry process and how breaking dependencies can lead to faster completion.

BREAKING DEPENDENCY CHAINS:
    Definition: 
        -> Breaking the dependency chain involves finding ways to make tasks less dependent on each other, allowing for more concurrent or parallel execution.

    Reducing Wait Time: 
        -> By breaking dependencies, tasks can start execution even if their predecessors are not fully completed.

STRATEGIES to BREAK DEPENDENCIES:
    + Overlapping Execution: 
        -> INSTEAD of WAITING for ONE TASK TO COMPLETE BEFORE STARTING THE NEXT, 
        tasks can OVERLAP or OCCUR SIMULTANEOUSLY.

    + Parallel Execution: 
        -> If TASKS are INDEPENDENT, they can be EXECUTED in PARALLEL on MULTIPLE PROCESSORS or cores.

    + Speculative Execution: 
        -> Tasks that are likely to be needed in the future can be started before it is certain that they will be required.

BENEFITS of BREAKING DEPENDENCY CHAINS:
    + Increased Concurrency: 
        -> Breaking dependencies allows for more tasks to be in progress simultaneously, potentially speeding up the overall process.
    + Reduced Idle Time: 
        -> Without strict dependencies, there is less idle time where tasks are waiting for their predecessors to complete.