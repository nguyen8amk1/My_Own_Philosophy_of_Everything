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
Using ABSTRACTION to SPLIT computing SYSTEMS into COMPONENTS 
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
    -> When you install Linux, 
    you should CREATE at least one REGULAR USER in addition to the root user
    -> Your PERSONAL ACCOUNT 

    1. The Shell Window (Terminal): 
        -> when the Terminal open it STARTS a SHELL INSIDE THE WINDOW. 

    2. Command: cat (conCATination)

        OUTPUTS the CONTENTS of:
            -> ONE or MORE FILES 

        general SYNTAX: cat file1 file2 ...

    3. Standard Input (stdin) and Standard Output (stdout): 
        Unix PROCESSES use: I/O STREAMS 
        to: 
            + read 
            + write 
            data

        PROCESSES: 
            READ data from an INPUT STREAM 
            WRITE data from an OUTPUT STREAM 

        STREAMS are very FLEXIBLE,

        vd: the SOURCE of an INPUT STREAM can be: 
            + a file
            + a device 
            + a terminal 
            + OUTPUT STREAM from ANOTHER PROCESS. 
        
        vd: Enter cat without filenames
        -> cat now READ from the STANDARD INPUT STREAM (provided by the Linux kernel)
            -> STANDARD INPUT was CONNECTED to the TERMINAL.
        -> rather than READ from the STREAM CONNECTED to a FILE

        "cat" command always WRITES its OUTPUT to the STANDARD OUTPUT.
        When you run "cat" in the terminal, the STANDARD OUTPUT is CONNECTED to that TERMINAL 
        -> you saw the OUTPUT on the TERMINAL

        
        **NOTE: 
            Many commands,
                if you DON'T SPECIFY INPUT FILE -> the commands READS from STDIN 
                Output is a little different, send output ONLY to STDOUT 
                    But others have options to send output directly to files.

        One of the BEST FEATURES of STANDARD STREAMS: 
            EASILY MANIPULATE THEM, to READ, WRITE to places other than the terminal 
            -> how to CONNECT STREAMS to FILES and other PROCESSES

        Further notes: [Unix Standard Input/Output](../blogs/Unix_Standard_Input_Output.md)

NOTE: 
    CTRL d: 
        -> STOP the current STANDARD INPUT ENTRY from the terminal 
        -> Affect current standard input entry (NOT INTENTIONALLY TERMINATE THE PROGRAM)

    CTRL c: 
        -> TERMINATES A PROGRAM regardless of its input or output.

### 2.3 Basic Commands 
    Most Unix commands take MULTIPLE: 
        + ARGUMENTS 
        + OPTIONS
        + FORMATS 

    We're just going LOOK at them at their MOST BASIC USAGE 
            
    + Command: ls 
        -> LIST the CONTENTS of a DIRECTORY(default is the current directory)    
        use options: 
            + -l: 
                -> long(DETAILED) listing 
            + -F: 
                -> display FILE TYPE INFORMATION
    + Command: cp
        + simplest form: COPIES(content) FILES
            vd: copy file1(content) to file2 
            -> cp file1 file2 

        + Copy A NUMBER OF FILES to a DIRECTORY 
            vd: cp file1 file2 dir 

    + Command: mv
        + simplest form: RENAMES A FILE 
            vd: rename file1 into file2
            -> mv file1 file2
        + Move A NUMBER OF FILES to a to a different directory: 
            vd: mv file1 file2 dir 
        

    + Command: touch 
        -> CREATES a FILE 
        If: the file already exists.   
            -> file existed file content does not change 
            -> **BUT: it UPDATED the file modification time stamp (printed with the ls -l command) 
    
    + Command: rm 
        -> REMOVE(delete) a file

        NOTE: After you remove a file, 
              it's gone from your system and generally can't be unremove

    + Command: echo
        -> PRINTS its ARGUMENTS to the STDOUT 
        vd: echo Hello again
            -> Hello again.

        NOTE: 
            echo is VERY USEFUL for FINDING:
                + EXPANSIONS of shell GLOBS (vd: *)
                    vd: echo * 
                        ->  will list everything in your directory (kinda like ls) 

                + VARIABLES (vd: $HOME)

### 2.4 Navigating Directories
    Unix has a DIRECTORY HIERARCHY that STARTS AT / aka "root directory"
    -> There are several STANDARD SUBDIRECTORIES in the ROOT DIRECTORY (vd: /usr)

    When you REFER to a FILE or DIRECTORY 
        -> specify a PATH or PATHNAME

    Parent of a directory: ../

    ABSOLUTE path: the path the STARTS WITH /
    RELATIVE path: the path the not STARTS WITH /

    + Command: cd
        CURRENT WORKING DIRECTORY: is the DIRECTORY that a PROCESS (vd: shell) is CURRENTLY IN. 
        -> cd = CHANGE CURRENT DIRECTORY
        If: omit dir -> the shell returns to your home_directory
        
    + Command: mkdir
        -> mkdir: MAKE NEW DIRECTORY

    + Command: rmdir
        vd: rmdir dir 
        -> removes the EMPTY directory
        -> if not empty -> command failed :v (STUPID :v)

        **Using rm -rf instead: 
            options: 
                -r: recursive delete to repeatly delete everything inside dir 
                -f: forces the delete operations

            **NOTES(IMPORTANT): 
                this is one of few commands that can do SERIOUS DAMAGE
                DON'T USE the -rf flags with GLOBS such as a *  

    + Shell Globbing (Wildcards) (Very cool)
        SHELL can:
            + MATCH simple PATTERNS to: 
                + file names
                + directory names
            -> the PROCESS OF MATCHING PATTERNS called: GLOBBING
            -> Similar to the concept of WILDCARDS in other systems.
    
        GLOB CHARACTERS: 
            + *
                -> MATCH ANY NUMBER of ABITRARY CHARACTERS
                -> the SHELL :
                    1. 
                        + MATCHES: ARGUMENTS containing globs 
                        + TO: FILENAMES
                    2. 
                        + SUBSTITUDES: the FILENAMES 
                            -> the SUBSTITUTION process called: EXPANSIONS
                        + FOR: those ARGUMENTS

                Some ways to use * to expand filenames: 
                    +  at* -> expands to all filenames that START with at  (vd: attent, attick,...)
                    + *at  -> expands to all filenames that END with at    (vd: flat, twat,...)  
                    + *at* -> expands to all filenames that CONTAIN at (vd: ditmesatgon, ...)

                NOTE: 
                    If: NO FILES MATCHES a glob -> the SHELL PERFORMS NO EXPANSION 
                    -> the commands still got the * in the arguments since there are no SUBSTITUTION
                        vd: echo *sdfjskdfjk
                            -> *sdfjskdfjk (the command just got the original arguments since the SHELL does not done any EXPANSIONS before hand)

                    In the Unix SHELL:  
                        the command: echo *.*
                        only match files and directories with the dot(.) in their NAMES 
                        -> the dot does NOT MEAN to CHECK FOR EXTENSIONS or anything 
                        Unix FILENAMES do NOT NEED EXTENSIONS, and often do not carry them. ?? 
            + ? 
                -> INSTRUCTS the SHELL to MATCH EXACTLY ONE ABITRARY CHARACTER 

                vd: b?at matches -> boat, brat 
                    -> only 1 CHARACTER get SUBSTITUDES into the ? 
                                 
            There are still a lot more Glob Characters 

            NOTE(IMPORTANT): 
                -> **Remember that the SHELL PERFORMS EXPANSIONS BEFORE running COMMANDS
                -> If you DON'T WANT the SHELL to EXPAND a glob in a command 
                    -> ENCLOSE the glob inside ''
                        vd: echo '*'

### 2.5 INTERMEDIATE(trung binh, kho dung hon cai truoc 1 xiu :v) Commands  
    + Command: grep: 
        -> PRINTS the LINES from:
            + files
            + input stream 

            that MATCHES an EXPRESSION
        vd: Print a the lines in the /etc/passwd file that contain the text "root" 
            -> grep root /etc/passwd

        -> SUPER HANDY when operating on MULTIPLE FILES at once 
        MOST IMPORTANT OPTIONS: 
            + -i: case-INSENSITIVE matches 
            + -v: invert the search 
                -> print all lines that DON'T MATCH 
                
        egrep is another POWERFUL VARIANTS of grep 

        grep UNDERSTANDS:
            + REGULAR EXPRESSION 
                (more powerful than wildcard-style pattern)
                (have different syntax)
                2 things to understand: 
                    + .* : matches ANY NUMBER OF CHARACTERS 
                    + .  : matches ONE ABITRARY CHARACTER

        **NOTE: some BOOKS about REGULAR EXPRESSION: 
            + Mastering Regular Expression
            + Programming Perl, regular expression chapter 
            + Introduction to Automata Theory, Languages and Computation (for MATH of regular expression)
            

    + Command: less: 
    + Command: pwd: 
    + Command: diff: 
    + Command: file: 

    + Command: find: 
    + Command: locate: 

    + Command: head: 
    + Command: tail: 

    + Command: sort: 

    + Command: passwd: ??Don't know how to actually use it 
    + Command: chsh: ??Don't know how to actually use it 

### 2.6 CHANGING your PASSWORD, SHELL
    ... 
### 2.7 Dot Files 
    ... 
### 2.8 ENVIRONMENT and SHELL VARIABLES 
    ... 
### 2.9 The Command PATH 
    ... 
### 2.10 SPECIAL Characters
    ... 


### 2.11 Command-Line Editing 
### 2.12 Text Editor 

### 2.13 Getting Online Help
    ... 
### 2.14 Shell Input and Output
    ... 
### 2.15 Understanding Error Messages 
    ... 
### 2.16 Listing and Manipulating Processes
    ... 
    1. Command Options: 
    2. KILLING Processes: 
    3. Job Control: 
    4. Background Processes: 

### 2.17 File Modes and Permissions
    ... 
    1. Modifying Permissions
    2. Symbolic Links
    3. Creating Symbolic Links 

### 2.18 ARCHIVING and COMPRESSING Files 
    ... 
    1. gzip 
    2. tar 
    3. Compressing Archives (.tar.gz)
    4. zcat 
    5. Other Compression Ultilities  

### 2.19 Linux DIRECTORY HIERARCHY Essentials 
    ... 
    1. Other Root Subdirectories 
    2. /user Directory 
    3. Kernel Location 

### 2.20 Running Commands as the Superuser
    ... 
    1. sudo 
    2. /etc/sudoers


## CHAPTER 3: Devices
... 
