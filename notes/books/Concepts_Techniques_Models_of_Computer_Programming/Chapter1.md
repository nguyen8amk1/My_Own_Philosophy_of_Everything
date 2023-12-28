## CHAPTER 1: INTRODUCTION TO PROGRAMMING CONCEPTS 
NOTE: **These code examples applies directly to the Mozarts Programming system

### 1. Variables      
    -> are just SHORTCUTS for VALUES 
    -> CAN'T be ASSIGNED more than once ( ~~ const)
    -> CAN DECLARE another variable with the SAME NAME as previous one 
        -> the PREVIOUS VARIABLE then become INACCESSIBLE 
        -> the PREVIOUS CALCULATION that used it are NOT CHANGED 

    + 2 CONCEPTS: 
        + IDENTIFIER:   
            -> the NAME of a VARIABLE (Start with capital letter followed by any number of letters of digit)  
            -> what the PROGRAMMER USES  
            
        + STORE VARIABLE: 
            -> part of SYSTEM'S MEMORY, store variable value 
            -> what the SYSTEM USES to calculate with 

    **"declare" statement: 
        -> CREATE: a NEW STORE VARIABLE 
        -> REFER/BIND: the IDENTIFIER to the new STORE VARIABLE

        -> **PREVIOUS calculations using the same indentifier are not changed  
            -> because the identifier REFERS to ANOTHER STORE VARIABLE 

### 2. Functions      
    + Functional abstraction: 
        -> Use EXISTING functions when DEFINING NEW functions

### 3. Lists      
    NOTE: 
        + Empty list = nil (for historical reasons)

    + List: a SEQUENCE of elements 
        vd: [1, 2, 3, 4] 

        + The notation: [1, 2, 3, 4] is just a SHORTCUT 
            -> it actually a CHAIN of LINKS: 
            ->  each LINK, contains 2 things: 
                + a list ELEMENT
                + a REFERENCE to the rest of the chain.

        + Always created 1 element at a time 
            -> starting with "nil" and adding link 1 by 1
            -> a NEW LINK is written: H|T
                + H: new element 
                + T: old part of the chain
            vd: 
                Z = nil 
                Y = 7|Z -> [7]
                X = 6|Y -> [6, 7]

                -> TAKEN the link APART, get back the HEAD or TAIL: 
                    use operator '.': 
                        "X.1": give the head: 6
                        "X.2": give the tail: [7]

        Terminologies: 
            + the LINK H|T: "cons", list pair 
            + CREATING a new link: "consing"

    + PATTERN MATCHING: 
        a MORE COMPACT WAY to TAKE APART a list 
            -> "case" instruction
                -> gets both HEAD and TAIL in ONE STEP
        vd: 
        declare
        L=[5,6,7,8]
        case L of H|T then {Browse H} {Browse T} end 

        -> **DECOMPOSE L according to the "pattern" H|T

### 4. Functions over Lists

    TOP-DOWN SOFTWARE DEVELOPMENT: 
        -> The Methodology of:
                + first WRITING the MAIN FUNCTION
                + FILLING in the BLANKS AFTERWARDS 

        Steps: 
            1. UNDERSTAND how to do the calculation BY HAND

            2. Write a main function to solve the problem 
                **ASSUMING that the AUXILIARY FUNCTIONS are KNOWN (vd: ShiftLeft, ShiftRight, AddList,...)

            3. Complete the solution by writing the auxiliary functions

### 5. Correctness
    How can we tell whether a program is correct ?     
        -> to PROVE CORRECTNESS in GENERAL, 
        **we have to REASON about the PROGRAM. 
        -> means 3 things: 
            + 1. LANGUAGE'S SEMANTICS: 
                -> Mathematical MODEL of the OPERATIONS of the PROGRAMMING LANGUAGE 
                -> The Model - DEFINING what the OPERATIONs should DO 
            + 2. PROGRAM'S SPECIFICATION: 
                -> What we would like the program to do. 
                -> Mathematical definition of: 
                    + the INPUTS that the program NEEDS
                    + the OUTPUT that the program CALCULATE 
            + 3. REASON ABOUT THE PROGRAM: 
                -> using MATHEMATICAL TECHNIQUES  
                -> DEMONSTRATES that the program SATISFIES the SPECIFICATIONS

    + Mathematical INDUCTION: 
        + 2 steps: 
            + 1. show that the program is correct for SIMPLEST CASE.
            + 2. show that: 
                    IF the program is CORRECT for a GIVEN CASE
                    THEN it is CORRECT for the NEXT CASE 

                If we can be sure that: ALL CASES are eventually COVERED.
                    -> can concludes that the program is ALWAYS CORRECT.

        **This technique can APPLIED for INTEGERS and LISTS:  
        vd: 
            + Integers: 
                1. Simplest case: 0 
                2. Given integer: n 
                    -> next case: n + 1
            + Lists: 
                1. Simplest case: nil
                2. Given list: T
                    -> next case: H|T (with no condition on H)

        Test the Induction method on the Fact function: 
            declare 
            fun {Fact N}
                if N == 0 then 1 
                else N*{Fact N - 1} end 
            end 
            
            1. Show that the program is CORRECT for SIMPLEST CASE: 
                **{Fact 0} -- (N = 0) return 1  -> Correct 
            2. show that: 
                    IF the program is CORRECT for a GIVEN CASE (N-1)
                        -> **ASSUME that {Fact N-1} is CORRECT

                    THEN it is CORRECT for the NEXT CASE (N)
                        -> when call {Fact N} 
                            the function will PERFORM this CALCULATION: N*{Fact N-1} 
                            -> We know/assume that:
                                + {Fact N-1} is correct
                                + the MULTIPLICATION is correct
                            -> {Fact N} return the RIGHT ASNWERS

### 6. Complexity
    **"Knowing the exact time is LESS IMPORTANT 
    than knowing that the TIME will NOT BLOW UP with INPUT SIZE"

    TIME COMPLEXITY: 
        -> The EXECUTION TIME of a program AS a FUNCTION OF INPUT SIZE, 
            up to a constant factor.   

### 7. Lazy evaluation
    + EAGER evaluation (DATA-DRIVEN evaluation): 
        -> do their calculation as soon as they are called. 

    + LAZY evaluation (DEMAND-DRIVEN evaluation): 
        -> calculation DONE ONLY WHEN IS NEEDED.

        vd: 
            fun lazy {Ints N}
                N | {Ints N + 1}
            end

            -> if this in eager evaluation mode  
                -> this will run infinitely 
            but we have the "lazy" keyword 
                -> ENSURES that the function will ONLY EVALUATED when it is NEEDED.
    
        ->  **ADVANTAGES: 
            + can CALCULATE with potentially INFINITE DATA STRUCTURE 
            WITHOUT any loop BOUNDARY CONDITIONS.
            + avoids redoing all the work. 
                vd: calculate the pascal triangle
                    + eager evaluation: {Pascal 10} 
                        -> the function calculate the from 0 to 10 
                        -> if we call {Pascal 11} -> will have to RECALCULATE everything from 0 to 11

                    + lazy evaluation: L = {Pascal} 
                        -> L.1 the function will AUTOMATICALLY CALCULATE the first row 
                        -> L.2.1 the function will AUTOMATICALLY CALCULATE the second row 

        vd: 
            L = {Ints 0}
            {Browse L} -> this will print L<Future> (no element get printed)
                -> If some elements of the L are needed,
                 then this function will be CALLED AUTOMATICALLY.
            {Browse L.1} -> display the first element (it will print out 0)
            
            case L of A|B|C_ then {Browse A + B + C} end
                this will prints the FIRST THREE ELEMENTS of L to be CALCULATED and NO MORE.

    
### 8. Higher-order Programming
    -> The ability to: 
        + PASS FUNCTIONS AS ARGUMENTS 
        + RETURN FUNCTIONS AS RESULTS

### 9. Concurrency 
    -> a Program have several INDEPENDENT ACTIVITIES,
                        each EXECUTES at its OWN PACE.
        There should be: NO INFERENCE AMONG THE ACTIVITIES 
        UNLESS the programmer decides that the ACTIVITIES need to COMMUNICATE there are 
        
    Introduce concurrency by creating THREADS.
    THREAD: 
        executing program like the functions that we saw before. 
    A program can HAVE MORE THAN 1 THREAD
    **we can call a function inside its own thread: 
        -> the function will NOT STOP other calculations from doing their jobs.
        vd: 
            thread P in 
                P = {Pascal 30}
                { Browse P }
            end 
            {Browse 999}
        -> We call { Pascal } inside its own thread.  
        -> The {Pascal} may run slow but it will not prevent {Browse 999} from running immediately (since it's fast :v)

### 10. Dataflow
    + DATAFLOW, a BEHAVIOUR what works like this:
        -> if an OPERATION tries to USE A VARIABLE that is NOT yet BOUND.  
            -> it WILL just WAIT
            -> maybe until some other thread will bind that variable, then the operation can continue. 

    + DATAFLOW and CONCURRENCY TOGETHER:
        vd:
            declare X in 
            thread {Delay 10000} X=99 end  -> X BINDING in Thread A
            {Browse start} {Browse X*X}   -> X PRINTING in Thread B

            declare X in 
            thread {Browse start} {Browse X*X} end  -> X PRINTING in Thread A
            {Delay 10000} X=99                      -> X BINDING in Thread B

        -> 1. The calculation work correctly INDEPENDENT of HOW they are PARTITIONED between threads.  
        -> 2. Calculations are patient, they do NOT SIGNAL ERRORS, but simply WAIT 

    **Key property: 
        + As long as the SAME OPERTATION are INVOKED with the SAME ARGUMENTS, ?? 
            -> it does NOT CHANGE the program's RESULTS at all.
        -> DATAFLOW CONCURRENCY GIVE MOST OF THE ADVANTAGES OF CONCURRENCY without the complexities that are usually associated with it. 

### 11. Explicit State
    + Explicit state: 
        -> The memory that needed for functions that can:
            + CHANGE their BEHAVIOUR 
            + LEARNING from their PAST 

    + Memory CELL: 
        -> Simplest way to define explicit state, a single memory cell.
        -> Many programming language call this "variable"
        -> We call it 'cell' to avoid confusions with the term 'variable' that we define previously
            -> our 'variable' means: Mathematical variable - SHORTCUTS FOR VALUES

        + 3 functions: 
            + CREATE a new cell 
            + ASSIGNMENT - PUTS a NEW VALUE in a cell 
            + ACCESS - gets the CURRENT VALUE stored in the cell 

    + Memory STORE: 
        -> a SERIES of MEMORY CELLS
        -> NUMBERED from 1 to n 

        + 4 functions: 
            + NewStore: 
                -> create a new store 
            + Put: 
                -> put a new value in a memory CELL 
            + Get: 
                -> get the current value stored in a memory CELL   
            + Size: 
                -> return the highest-numbered cell used so far
                    basically max_index 
        vd: 
            declare
            S = {NewStore}
            {Put S 2 [22 33]} -> store [22 33]  in memory cell 2
            {Browse {Get S 2}} -> display [22 33]
            {Browse {Size S}} -> display 2 (the max_index)


### 12. Objects 
    + Object: 
        -> a FUNCTION with INTERNAL MEMORY 

    + Encapsulation: 
        -> Implies that: users cannot mess with the function's/object's internals
        -> GUARANTEE that the counter will ALWAYS WORK CORRECTLY no matter how it is used.  
            -> as long as the INTERFACE of the object is the SAME  
                -> the user program DOESN'T NEED TO KNOW the IMPLEMENTATION
            -> the SEPARATION of: 
                + INTERFACE
                + IMPLEMENTATION
                -> the Essence of Data Abstraction 
    
    + Polymorphism: 
        -> A programs that use an object will WORK CORRECTLY for ANY IMPLEMENTATION    
           as long as the INTERFACE is the SAME. 

### 13. Classes
    + Class: 
        -> A FACTORY that can make as many objects as we need. 
        -> It's basically a FUNCTION that RETURNS a FUNCTION (with internal state) - ie: an object 
            -> higher-order programming =))

    + Toward OOP:
        A class can be used to make as many objects as we need. 
        -> All these objects:
            + SHARE: SAME methods
            + OWN: SEPARATE internal memory 

        Programming with: 
            + classes
            + objects
            = OBJECT-BASED PROGRAMMING

        OOP =  Object-based programming + INHERITANCE

        + INHERITANCE: 
            -> NEW CLASS can be DEFINED in terms of EXISTING CLASSES 
                -> by SPECIFYING: HOW the NEW CLASS is DIFFERENT
            -> Powerful CONCEPTS for STRUCTURING program
            -> let's a class be DEFINED INCREMENTALLY, in different parts of the program  
            
### 14. Nondeterminism and time
    Having both: 
        + concurrency
        + state
        -> at the SAME TIME is TRICKY 
            because the SAME PROGRAM can give DIFFERENT RESULTS from one execution to the next. 
                -> NONDETERMINISM 

    + Nondeterminism: 
        -> exists because we LACK KNOWLEDGE of the EXACT TIME when each basic OPERATION EXECUTES 
            -> Because the THREADS are INDEPENDENT
                -> Since they KNOW NOTHING OF EACH OTHER 
                    -> they DO NOT KNOW WHAT INSTRUCTIONS each has EXECUTED. 
        -> Nondeterminism BY ITSELF is NOT A PROBLEM (we already have it with concurrency)
        -> The problem occurs when it's OBSERVABLE (shows up in programs) 
            Observable Nondeterminism = Race Condition
            vd: 
                declare 
                C = {NewCell 0}
                thread
                    C := 1
                end 
    
                thread
                    C := 2
                end 

                -> When the program runs, we can't be sure that the result will be 1 or 2,
                    since we don't know which thread will run first
                -> This is a SIMPLE CASE of OBSERVABLE NONDETERMINISM

    + Interleaving:
        -> Threads TAKE TURNS each executing a little.

        vd: 
            declare 
            C = {NewCell 0}
            thread I in 
                I = @C
                C := I + 1
            end 

            thread J in 
                J = @C
                C := J + 1
            end 
            -> the program can run I = @C but then run J = @C, 
                they're NOT FORCE to RUN the ALL THE CODE one after another in each thread,
                they can run little by little interchangeably

        -> More complicated programs have many more possible interleavings. 
        -> **Programming with CONCURRENCY and STATE together is basically a questions of MASTERING the INTERLEAVINGS
    
        NOTE: 
            if at all possible: DO NOT USE STATE AND CONCURRENCY TOGETHER  
            -> actually we OFTEN DO NOT NEED BOTH together 

### 15. Atomicity 
    + Atomic: 
        -> an operation is atomic if NO INTERMEDIATE STATES can be OBSERVED. 
        -> "it seems to" JUMP DIRECTLY from INITIAL STATE to RESULT STATES -> no intermidiate state
        -> A way to MAKE programming with CONCURRENCY and STATE EASIER  
            -> use ATOMIC OPERATIONS
                -> can SOLVE INTERLEAVING PROBLEM. 

    + **Main Idea: 
        -> Make sure that each THREAD BODY is ATOMIC
        -> LOCK: 
            -> a way to build atomic operations.
            + 2 regions: 
                + inside 
                + outside  

            + property: 
                -> only 1 THREAD at a time can be EXECUTING in the INSIDE region.
                    -> what happens INSIDE the lock as atomic. 

                    -> if the SECOND thread TRIES TO GET IN, 
                        it will WAIT until the FIRST GETS OUT 
            + 2 operations: 
                + CREATE new lock
                + DEFINE the lock's INSIDE region
                    with instruction: lock L then .. end. 

        vd: 
            declare 
            C = {NewCell 0}
            L = {NewLock}
            thread
                lock L then I in 
                    I = @C
                    C := I + 1
                end
            end 

            thread
                lock L then J in 
                    J = @C
                    C := J + 1
                end 
            end 

        **NOTE: 
            BOTH THREAD BODIES have to be GUARDED BY THE SAME LOCK  
    NOTE: 
        concurrent != parallel 
        concurrent: 
            -> multiple threads or processes are making progress, 
               their execution may OVERLAP IN TIME. 
                The system may SWITCH between THREADS, 
                    -> giving the APPEARANCE of SIMULTANEOUS EXECUTION. 
                    This can ENHANCE RESPONSIVENESS and RESOURCE UTILIZATION. 

            there only 1 TIME LINE THAT EVERYTHING RUN ON 
            and different threads can participate in parts of the timeline 

### 16. Where to we go from here ? 
    This chapter has introduced the following COMPUTATION MODELS: 
        + Declarative model: 
            -> defines mathematical functions 
            -> mathematical functions are easy to:
                + reason about
                + test 

        + Concurrent declarative model:
            -> Declarative model + DATAFLOW concurrency
            -> allows a more flexible, incremental execution

        + Lazy declarative model: 
            -> Declarative model + Laziness
            -> allows: 
                + calculating potentially INFINITE DATA-STRUCTURE
                    -> good for:
                        + resource management
                        + program structure 

        + Stateful model: 
            -> Declarative Model + Explicit State 
            -> allows:
                    + writing programs whose BEHAVIOUR CHANGES OVER TIME. 
            -> good for: 
                    + program MODULARITY

            If written well: (vd: using ENCAPSULATION and INVARIANTS)
                -> these programs are almost as EASY to REASON about as declarative programs. 

        + Object-oriented model: 
            -> a programming style for STATEFUL PROGRAMMING with DATA ABSTRACTIONS.
            -> Make easy to use POWERFUL TECHNIQUES such as:
                + Polymorphism 
                + Inheritance
                        
        + Shared-state concurrent model: 
            -> Concurrency (Concurrent declarative model) + Explicit State (Stateful Model)
            -> If programmed carefully, 
            using TECHNIQUES of MASTERING INTERLEAVING such as: 
                + MONITORS
                + TRANSACTIONS
                ...
            -> gives both the advantages of both stateful and concurrent models. 

### Excercise @TODO
    ... 
    3. Program correctness: 
        ... 
    7. Variables (shortcut for values) vs memory cells: 
        ...
    8. Using explicit state and functions: 
        ...
    9. ... 
