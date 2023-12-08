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


### 1.2: LEVELS and LAYERS of ABSTRACTION in Linux System 
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
    
    



### 1.3: HARDWARE: Understanding the Main Memory 
    ...

### THE KERNEL
    ...

### USERSPACE 
    ...

### USERS 
    ...
