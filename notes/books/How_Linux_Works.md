# HOW LINUX WORKS 
notes from book: HOW LINUX WORKS (by: Brian Ward) 
https://ia801706.us.archive.org/14/items/linux-books/How%20Linux%20Works%202nd%20Edition.pdf

## PREFACE 
You should be able to make your software do what you want it to do 
(within the reasonable limits of its capabilities)

-> the KEY to ATTAINING THIS POWER: 
    -> UNDERSTANDING the FUNDAMENTALS of: 
        + WHAT the software does 
        + HOW It works

-> Linux DOESN'T HIDE anything from you 
    + Most system CONFIGURATION can be found in PLAINTEXT FILES 

    -> the only TRICKY PART is: 
        + Figuring out WHICH PARTS are RESPONSIBLE for WHAT and HOW it all FITS TOGETHER. 

## CHAPTER 1: THE BIG PICTURE 
The most EFFECTIVE WAY to UNDERSTAND HOW AN OPERATING SYSTEM WORKS: 
    -> ABSTRACTION: ignore most of the details 
    -> For different type of users,
    the amount of knowledge you need for doing something is different 

    vd: as a Car PASSENGER 
    -> Only need to understand: 
        + What it does
        + How to use it 

    but as a car DRIVER: 
        You need to know more:  
        + How to OPERATE THE CONTROLS
        + What to do when something goes wrong. 
    -> **WE ARE THE DRIVER  

    vd: When the car ride is rough: 
        -> Break up the abstraction of "a car that rolls on a road"
        into 3 parts: 
            + car 
            + road
            + the way that you're driving 
        -> Isolate the system: 
        If the road is bumpy -> can't blame the car 
        -> focus on the road, why the workers done their job so poorly  

    Software developer USE ABSTRACTION as a TOOL: 
        -> when building a software component,
        DON'T CARE about the INTERNAL STRUCTURE OF OTHER components.
        DO CARE: 
            + WHAT OTHER COMPONENTS they CAN USE 
            + HOW TO USE them.


### 1.1: LEVELS and LAYERS of ABSTRACTION in Linux System 
Using Abstraction to SPLIT computing systems into components 
    -> Makes thing easier to understand 

BUT it DOESN'T WORK without ORGANIZATION   
-> Arrange components into LAYERS  
-> Layers: classification of a component 
according to WHERE that component SITS BETWEEN the USER and the HARDWARE

-> Linux has 3 MAIN LAYERS:
    + Hardware:  
        + CPU 
        + Memory 
        + Devices: 
            + Disk
            + Network Interface
    + Kernel:  
        is SOFTWARE in main memory: 
        that tells the CPU: WHAT TO DO
        Manages: 
            + Hardware 

        Acts as INTERFACE between: 
            + hardware 
            + any running program 
        vd: 
            + System calls 
            + Process Management
            + Memory Management
            + Device drivers 
        
    + (User) Process: 
        running programs that kernel manages 
        -> all of these programs run in "USER SPACE"

        All user space process is user process,
        no matter it was directly interact with user or not
        vd: 
            + GUI 
            + Servers
            + Shell
    
Kernel vs User Process: 
    critical difference: 
        the way that they run 

    Kernel:
        + runs in "kernel mode"    
        + has UNRESTRICTED ACCESS to:
            + PROCESSOR 
            + main MEMORY 
        -> pros: POWERFUL. 
        -> cons: allows Kernel to easily crash the entire system.

        -> KERNAL SPACE: The area that only kernel can access 
    

    User processes:
        + run in "user mode" 
        + RESTRICT ACCESS to:
            + a (small) SUBSET OF MEMORY 
            + safe CPU OPERATIONS

        -> pros: if a process crash, it won't take down the whole system, 
                and the mess can be cleaned up by the kernel 

        -> USER SPACE: the parts of main memory that the user process can access. 
    

### 1.2: HARDWARE: Understanding the Main Memory 
MAIN MEMORY is perhaps THE MOST IMPORTANT
CPU is just an OPERATOR on memory 
    + READ: 
        + instruction
        + data 
        from the memory 

    + WRITE:
        + data 
        to the memory  

State: is just a particular arragment of bits 
    vd: 0100, 0100, are different states 

NOTE: 
    "it commmonly refer to the STATE in ABSTRACT TERMS
    rather than to the ACTUAL BITS
    -> the term IMAGE: refer to a particular physical arrangement of bits"


### 1.3: THE KERNEL
Nearly EVERYTHING that the KERNEL DOES revolves around MAIN MEMORY 
vd: 
    + SPLIT memory into many SUBDIVISIONS
    + MAINTAIN certain STATE INFORMATION about those SUBDIVISIONS at all times
    + Ensure the process only use it's own share of memory 
    
Kernel manage 4 SYSTEM AREAS: 
    + Processes: 
        DETERMINE WHICH PROCESSES are ALLOWED TO USE THE CPU. 
    + Memory: 
        KEEP TRACK of ALL MEMORY: 
            + what is currently ALLOCATED to a particular process
            + what might be SHARED between processes
            + what is FREE

    + Device drivers: 
        acts as INTERFACE between HARDWARE (vd: disk) and PROCESSES
        KERNEL job to OPERATE the HARDWARE
            
    + System calls and support: 
        PROCESSES normally USE SYSTEM CALLS 
        to COMMUNICATE with the KERNEL

1.3.1: Process Management:     
    describe: 
        + starting 
        + pausing 
        + resuming 
        + terminating 
        of processes
    The processes do not run at exactly the same time. Even though it seems like it :v 
    FACT: 
        each process use a small fraction of a second 
        then pause
        then another process take turn and also use a small fraction of a second 

    Time slice: the small fraction of a second that the process use the CPU 
        -> give the process ENOUGH TIME for SIGNIFICANT COMPUTATION
            the task often FINISH the current TASK during a SINGLE SLICE 
    
    Context switch: the act of ONE PROCESS GIVING UP CONTROL of the CPU TO ANOTHER PROCESS
        -> the KERNEL is RESPONSIBLE for it 

    vd:
        CPU(hardware):  
            + 1. INTERUPTS the current PROCESS based on an INTERNAL TIMER.
                -> SWITCHES to KERNEL MODE, hands control back to the kernel 

        Kernel:
            + 2. RECORDS the CURRENT STATE of:
                + CPU 
                + MEMORY  
                -> essentially to RESUMING the PROCESS That was just interupted. 

            + 3. PERFORMS any tasks (syscalls) that might have been called from the previous process 
                (collecting data from I/O, ...)
                -> with every SYSCALL the PROCESS does have to WAIT until the KERNEL IN CHARGE for that call to be executed 

            + 4. ANALYZE the LIST OF PROCCESSES that are ready to run and CHOOSE ONE.

            + 5. PREPARE:
                + MEMORY for this new process, 
                + CPU

            + 6. SWITCHES the CPU into USER MODE 
                 hands the control of the CPU to the process

        -> ANSWERS the IMPORTANT QUESTION: 
            + WHEN the kernel runs: 
                it RUNS BETWEEN TIME SLICES during a context switch 


    In the case of multi-CPU system, things slighty more complicated (i don't care about it :v)
             

1.3.2: Memory Management:     
    THE KERNEL MUST MANAGE MEMORY DURING A CONTEXT SWITCH  

    These CONDITIONS must hold: 
        Kernel: 
            + the KERNEL must have its OWN PRIVATE AREA in MEMORY that USER PROCESSES CAN'T ACCCESS

        User process: 
            + EACH USER PROCESS needs its OWN SECTION in MEMORY 
            + ONE user PROCESS may NOT ACCESS the PRIVATE MEMORY of ANOTHER PROCESS. 
            + User process CAN SHARE MEMORY.
            + Some memory can be READ-ONLY

        The system can USE MORE MEMORY than is PHYSICAL PRESENT by using DISK SPACE AS AUXILIARY 

    ...virtual memory stuff @NotDone
    
1.3.3: Device Drivers and Management: 
    A device ACCESSIBLE only in KERNEL MODE 
    because:
        + IMPROPER ACCESS (vd: user process asking to turn off the power) 
            -> CRASH THE MACHINE 

        + different devices RARELY have the SAME PROGRAMMING INTERFACE.
            -> DEVICE DRIVERS present a UNIFORM INTERFACE to the user processes 
            -> Device drivers traditionally been part of the kernel 

1.3.4: System calls and support: 
    other kinds of Kernel features that are available to the user processes: 
        + System calls 
            -> PERFORM specific TASKS that USER PROCESS alone CANNOT DO well or at all 
            vd: open, read, write files

            -> is an INTERACTION between: 
                + process 
                + kernel

    2 IMPORTANT SYSTEM CALLS: 
        -> understand HOW PROCESS START UP

        + fork(): 
            1. a PROCESS: called fork()
            2. the KERNEL: CREATE (nearly) identical COPY of the PROCESS

        + exec(): 
            1. a PROCESS: called exec()
            2. the KERNEL: 
                STARTS program, 
                REPLACING the CURRENT PROCESS.  
    
    -> ALL user processes on Linux system START as a result of FORK();         
    -> then run EXEC() to start a new program. 

    vd: ls command: 
        1. User enter "ls" to the terminal 
        2. The SHELL running inside the terminal 
            CALL FORK() -> CREATE A COPY OF THE SHELL
        3. THE NEW COPY OF THE SHELL CALLED EXEC(LS) to run "ls"
        
    SUPPORT FEATURES: 
        + PSEUDODEVICES: 
            -> LOOK LIKE DEVICES(hardware) to user processes, 
            BUT they're IMPLEMENTED purely in SOFTWARE

    NOTE:
        -> a USER PROCESS that ACCESSES a PSEUDODEVICES 
        still HAS TO USE a SYSTEM CALL to OPEN THE DEVICE 

        -> PROCESSES CAN'T entirely AVOID SYSTEM CALLS 

### 1.4: USERSPACE 
    The MAIN MEMORY that KERNEL ALLOCATES for USER PROCESSES is called "User space". 
    Process is simple a state(image) in memory.    

    There are a LAYER STRUCTURE to user processses: 
        + Bottom Layers (closest to the kernel): 
            Basic services: small components that perform single, uncomplicated tasks. 

        + Middle layer: 
            Ultility services: larger components such as: mail, print, database services.

        + Top Layer:  
            Application that directly interactive with user 
            complicated tasks that user often control directly.

    If one component wants to use another components
    -> The second component is either at:
        + the SAME service LEVEL
        + the level BELOW

    In reality it's difficult to classify the layer of an application, 
    since it's just relative 

### 1.5: USERS 
    an ENTITY that CAN:
        + RUN processes 
        + OWN files
    
    associate with a: USERNAME
    BUT the KERNEL does NOT MANAGE USERNAME
    instead by IDENTIFY users by USERID
    
    Exist to SUPPORT:  
        + PERMISSIONS
        + BOUNDARIES 

    Every user-space process has a:
        + OWNER (user)
        -> the processes are said RUN AS THE OWNER

    User can: 
        + TERMINATE
        + MODIFY the behaviour of its own processes 
        + OWN FILES 
        + CHOOSE whether to SHARE the file with other users 
     
    Linux system has a number of users 
    in addition to the ones that correspond to the real human who use the system.

    the MOST IMPORTANT user is ROOT

    ROOT:
        + is an EXCEPTION to the 
            PERMISSIONS and BOUNDARIES rules

        + can:
            + terminate 
            + alter 
            another user's processes
            + read any file on the local system.

    GROUPS: SET of users 
        -> ALLOW user to SHARE FILE ACCESS to other users in a group.

## CHAPTER 2: BASIC COMMANDS and DIRECTORY HIEARCHY
### 2.1 The Bourne Shell:  /bin/sh
    The SHELL:
        -> a PROGRAM that RUNS COMMANDS 
        -> one of the MOST IMPORTANT part of a Unix system.  
        -> serve as a SMALL PROGRAMMING ENVIRONMENT 

    Unix programming often: 
        + BREAK COMMON TASKS into little COMPONENTS 
        -> use the SHELL to:
            + MANAGE tasks 
            + PIECE things TOGETHER

    SHELL SCRIPT: a FILE that contains a SEQUENCE OF SHELL COMMANDS  

    There are MANY different UNIX SHELLS: 
        all derive several of their features from the Bourne shell /bin/sh
        Every Unix system needs the Bourne shell in order to function correctly 

    Linux use an enhanced version of the Bourne shell called BASH, the "Bourne-again" shell
        -> is the default shell in Linux 
        -> /bin/sh on Linux is normally refer to BASH 

### 2.2 Using the Shell 
    The Shell Window: 
    Command: cat
    Standard Input and Standard Output: 

### 2.3 Basic Commands 
    Command: ls 
    Command: cp
    Command: mv
    Command: touch 
    Command: rm 
    Command: echo

### 2.4 Navigating Directories
    Command: cd
    Command: mkdir
    Command: rmdir

### 2.5 
