# CONCEPTS, TECHNIQUES, MODELS OF COMPUTER PROGRAMMING 
notes from book: CONCEPTS, TECHNIQUES and MODELS of COMPUTER PROGRAMMING, by PETER VAN ROY and SEIF HARIDI 
(i have physical books :) ) 

## PREFACE: 
    Study PROGRAMMING LANGUAGES as a WAY to LEARN COMPUTER PROGRAMMING: 
        -> give LITTLE INSIGHT into programming as a UNIFIED DISCIPLINE. 
            since there are so MANY PARADIGMS 

    -> We should FOCUS on: 
        + PROGRAMMING CONCEPTS
        + TECHNIQUES in USING those CONCEPTS
        NOT on PROGRAMMING LANGUAGES

    CONCEPTS - ORGANIZED in terms of COMPUTATION MODELS: 

        COMPUTATION MODEL: formal SYSTEM that DEFINES HOW COMPUTATION ARE DONE.
            MODELS are DEFINED in terms of CONCEPTS that are IMPORTANT to programmers, such as: 
                + Data types 
                + Operations
                + Programming language

            Each MODEL have it's own SET of TECHNIQUES for: 
                + PROGRAMMING 
                + REASONING 

            -> BASED ON: KERNEL LANGUAGE (simple core language) 
                -> Introduce in a PROGRESSIVE WAY (by ADDING the CONCEPTS ONE BY ONE).   
                -> Show the DEEP RELATIONSHIPS between the DIFFERENT MODELS 

                Adding just 1 new concept makes a world of difference in programming.
                    vd: Adding EXPLICIT STATE (destructive assignment) to FP
                        -> ALLOWS us to do OOP 

                + *WHEN should we ADD a CONCEPT to a MODEL ? 
                    -> Main criterion (tieu chuan) is: CREATIVE EXTENSION PRINCIPLE ->  
                        -> a NEW CONCEPTS is ADDED when PROGRAMS become COMPLICATED 
                            for TECHNICAL REASONS UNRELATED to the PROGRAM being solved.

                    -> *ADDING a CONCEPT to the KERNEL LANGUAGE can KEEP PROGRAMMING SIMPLE (if the concept is CHOSEN CAREFUL). 

                + *WHICH oncept should we add ? 

        *"COMPUTATIONAL MODEL" is more CONCRETE and WELL DEFINED than "PROGRAMMING PARADIGM" 

    WHAT programmers NEED: 
        + Programming TECHNIQUES 
        + Design PRINCIPLES 

        made possible by COMPUTATION MODELS

### GOALS OF THE BOOK: 
#### MAIN GOAL: 
    Teaching:
        + programming as a UNIFIED DISCIPLINE with a SCIENTIFIC FOUNDATION. 
        + how to design programming abstractions

#### Programming: 
    the act of EXTENDING/CHANGING a SYSTEM'S FUNCTIONALITY.
    -> DONE both BY: 
        + specialist: 
            vd: programmers
        + non-specialist: 
            vd: consumer who change the settings of ... 

    -> To Programmer: 
        Programming is the STEP between:
            + system's SPECIFICATION
            + RUNNING PROGRAMS that IMPLEMENTS the SPECIFICATION
            -> Consist in: 
                DESIGNING THE PROGRAM'S: 
                    + ARCHITECTURE
                    + ABSTRACTION 
                    + CODING 

        **Programming based on: 
            + CONCEPTS
            + concept's USAGES
            rather than PROGRAMMING LANGUAGE

            -> UNBIASED by LIMITATIONS of
                + particular LANGUAGE  
                + DESIGN METHODOLOGY (PP luan)

        When USED in SPECIFIC SITUATION, GENERAL VIEW is ADAPTED to the TOOLS used.
            (taking into account the TOOLS:
                + abilities
                + limitations)

#### Programming has 2 Essential PARTS: 
    + 1. TECHNOLOGY (current tools)
        consist of:
            + TOOLS: 
            + pratical TECHNIQUES: 
            + STANDARDS: 
            -> allow us to *DO* programming 
        

    + 2. SCIENTIFIC FOUNDATION (fundamental concepts)
        consist of:
            + BOARD theory 
            + DEEP theory  
            -> give PREDICTIVE POWER
            -> allow us to *UNDERSTAND* programming.

    The SCIENCE - EXPLAIN -> TECHNOLOGY in a WAY that is a DIRECT and USEFUL 

    If EITHER PART (tech or science) is LEFT OUT -> You're NO LONGER DOING PROGRAMMING ANYMORE.
        Without: 
            + TECHNOLOGY -> you're doing PURE MATHEMATICS
            + SCIENCE -> you're doing a CRAFT 
                -> Lack DEEP UNDERSTANDING

    "KNOWING THE TOOLS PREPARE FOR THE PRESENT. 
     KNOWING THE CONCEPTS PREPARES FOR FUTURE DEVELOPMENTS"    

#### More than a craft: 
    PROGRAMMING is almost always TAUGHT as a CRAFT 
    Taught in the CONTEXT of a PROGRAMMING LANGUAGE  
    there is a CONFUSION between TOOLS (Techology) and CONCEPTS (scientific foundation)

    -> different school of thought have developed
        -> based on DIFFERENT WAYS of VIEWING PROGRAMMING, called PARADIGM (vd: OOP, LOGIC, FUNCTIONALITY)
        -> each school of thought has its own SCIENCE 

    -> The unity of programming as a SINGLE DISCIPLINE has been LOST 
        -> Programs suffer from POOR DESIGN.  
            vd: Java Concurrency is very expensive 
                -> Java programmers CONCLUDE that CONCURRENCY is a fundamentally DIFFICULT

            Program SPECIFICATIONS are DESIGNED AROUND the DIFFICULTIES 
            BUT these(vd: Concurrency) DIFFICULTIES are NOT FUNDAMENTAL AT ALL

                vd: Java Concurrency is hard doesn't mean Developing a concurrency program is hard 
                -> There are better alternatives techniques to use 
                ** -> SHOULDN'T ADD the LOW-LEVEL DIFFICULTIES to the Program SPECIFICATIONS
                


    NOTE: 
    *Basically: 
        Programming should be view as a single block with 2 properties: 
            + Techology
            + Science
        But now its get DIVIDED into lots of SMALL CHUNKS of "sub-programming", 
        each with its own Techology and Science:  
            
        ** -> SHOULDN'T ADD the LOW-LEVEL DIFFICULTIES to the Program SPECIFICATIONS

#### The kernel language approach: 
    Practical Programming Language provide a Rich set of ABSTRACTIONS and SYNTAX.
    -> How can we SEPARATE the language's:
            + FUNDAMENTAL CONCEPTS (which underlie the language success).
            + Historical accidents 

        Kernel language approach shows 1 way:  
            -> TRANSLATE - PRACTICAL LANGUAGE into KERNEL LANGUAGE

        KERNEL LANGUAGE:
            + consist of: 
                + SMALL numbers of programmer-significant elements.
            + has: 
                + simple FORMAL SEMANTIC that allows REASONING about program's: 
                    + CORRECTNESS
                    + COMPLEXITY

        Languages and Programming Paradigms can be modeled by a subset of the kernel language 
            -> Every paradigms can be modeled by 1 big kernel language (-> Unity :v)

        **REDUCING a COMPLEX PHENOMENON to its PRIMITIVE ELEMENTS         
            is CHARACTERISTIC of the SCIENTIFIC METHODS

            -> successful approach that is used in all "exact sciences" (Google for more info).

            -> give DEEP UNDERSTANDING that has PREDICTIVE POWER. 
                vd: structural science lets one:
                        + DESIGN all bridges 
                        + PREDICTS all bridges behaviours in terms of SIMPLE CONCEPTS (such as: 
                            + force
                            + energy
                            + stress
                            + strain 
                            + laws that the simple concepts obey.   
                        )
                        
#### Comparisons with OTHER APPROACHES                
    + Foundational Calculus (vd: Lambda calculus,...):
        -> REDUCES programming into a MINIMAL NUMBER OF ELEMENTS.
        -> The elements are CHOSEN to:
                SIMPLIFY MATHEMATICAL ANALYSIS 
                NOT to AID programmer INTUITION
            -> better for theoreticians, NOT USEFUL for practical programmer
        -> USEFUL for: 
            + studying fundamental PROPERTIES and LIMITS of Programming 
            NOT for writing/reasoning general application

    + Virtual machine: 
        -> DEFINES a LANGUAGE in terms of an IMPLEMENTATION on an IDEALIZED MACHINE. 
        -> give OPERATIONAL SEMANTICS, with CONCEPTS that are CLOSE TO HARDWARE.
        -> USEFUL for: 
            + DESIGNING computers, doing SIMULATIONS 
            NOT for REASONING about PROGRAMS and their ABSTRACTIONS

    + Multiparadigm Language: 
        -> language that encompasses(bao gom) several programming paradigms. 
        -> USEFULNESS of a Multiparadigm language DEPENDS on: 
            HOW WELL the different paradigms INTERGRATED.

    -> The kernel language approach COMBINES FEATURES of ALL these APPROACHES. (@@ NOT EASY TO UNDERSTAND THIS PART)
        -> a well designed kernel language COVERS a WIDE RANGE OF CONCEPTS, (like a well designed MULTIPARADIGM LANGUAGE)

        -> if the CONCEPTS are INDEPENDENT -> kernel language can be given a SIMPLE FORMAL SEMANTICS (like a FOUNDATIONAL CALCULUS)

        -> FORMAL SEMANTICS can be a VIRTUAL MACHINE (at a HIGH LEVEL OF ABSTRACTIONS)
        
    -> Made easy for programmer to reason about programs 

        NOTE: 
            Basically: kernel language combines features: 
                + CONCEPTS of MULTIPARADIGM LANGUAGE
                + FORMAL SEMANTICS of FOUNDATIONAL CALCULUS
                + VIRTUAL MACHINEs of Virtual machine  ?? 

            Concepts -> Formal Semantics -> Virtual machines

#### Designing abstractions
    Teach how to design programming abstractions (the most difficult work)

    Programming a computer is primarily:
        + DESIGNING abstractions
        + USING abstractions 

        -> to ACHIEVE new GOALS 
        
    ABSTRACTION:
        -> uses as a TOOL that SOLVES a particular PROBLEM. 
        -> The SAME ABSTRACTIONS can be used to SOLVE many DIFFERENT PROBLEMS.
            -> VERSATILITY: one of the KEY PROPERTIES of abstractions

    Teaching APPROACH: 
        1. Start with Programming CONCEPTS
            -> RAW MATERIALS for building abstractions
            such as: 
                + lexical scoping 
                + higher order programming
                + compositionality 
                + encapsulation 
                + concurrency
                + exceptions
                + lazy execution 
                + security 
                + explicit state
                + inheritance
                + nondeterministic choice.

        2. Each CONCEPTS, give TECHNIQUES for building abstractions with it.

        3. General LAWS for building abstractions 
    
        Basically: CONCEPTS -> TECHNIQUES -> LAWS  

#### Main features
    + Pedagodical(giao duc) approach: 
        2 ways to teach programming as a rigorous(chinh xac) discipline:
            + Computational-based: 
                -> present programming as : a way to define EXECUTION ON MACHINE 
                + Formal semantics: in terms of ABSTRACT MACHINES

            + Logic-based: 
                -> present programming as : a branch of MATHEMATICAL LOGIC 
                -> LOGIC does NOT speak of EXECUTION 
                    BUT of program PROPERTIES
                    -> Higher level of abstractions ?? 

                + Programs: are mathematical CONSTRUCTS that OBEY LOGICAL LAWS.
                + Formal semantics: in terms of MATHEMATICAL LOGIC
                + Essential for: DEFINING precise SPECIFICATION of WHAT PROGRAMS DO.
                + Reasoning: done with LOGICAL ASSSERTION.  

    + Broad overview of computation models: 
        It's NOT TRUE that models with MORE CONCEPTS are BETTER or WORSE 
        New concepts is like a two-edge sword

        ADDING A CONCEPT to a computation model 
            -> introduces new forms of expressions 
                 + pros: making some PROGRAMS SIMPLER 
                 + cons: REASONINGS about programs HARDER 

            vd: Adding a explicit state (mutable variables) to FP model 
                -> pros: can do OOP in FP 
                -> cons: Reasoning about OOP is harder than FP 

    + IMPORTANCE of USING MODELS TOGETHER: 
        **"One does NOT programs with MODEls,
        But with:
            + programming CONCEPTS  
            + WAYS to COMBINE the programming CONCEPTS"

        -> Depend on which concepts one uses 
            -> consider the programming style in in which model 

        -> The MODELS appears as a SIDE EFFECTS 

    + LIMITS of single models: 
        A GOOD PROGRAMMING STYLE requires USING programming CONCEPTS 
        that are usually ASSOCIATED with DIFFERENT COMPUTATION MODELS 
        -> language that implemented only 1 computation model make programming difficult 

        vd: 
            + OOP: 
                -> encourages OVERUSE of:
                    + STATE
                        -> makes concurrency difficult  
                    + INHERITANCE
                        -> often get misused
                        -> violates separation of concerns
                    
            + FP: 
                -> OVERUSE of: 
                    + higher-order programming
                        vd: 
                            + monads: 
                                -> makes program intricate 
                                but does not achive modularity properties
                            + currying: 
                                ...

            + Logic: 
               ...

#### Teaching from the book: 
    3 core topics: 
        1. Concepts and Techniques
        2. Algorithms and Data Structure
        3. Program design and Software Engineering

    Note: 
        There is a STRONG INTERDEPENDENCY between 1. and 3.
            -> Concepts -> EXPRESS the DESIGN 
            -> Program design -> AVOID bad habits 
    Courses: 
        + Concepts and Techniques: 
            -> Chapter 1 - 8

        + Applied Programming Models: 
            -> Chapter 9 - 12

        + Concurrent Programming: 
            -> start with: chapters 2, 3, 6, 7
            -> then: chapters 4, 5, 8, 11

        + Computation models and their relationships: 
            -> Chapter 13

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
    -> The ability to: PASS FUNCTIONS AS ARGUMENTS 

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
    + DATAFLOW:
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
        + Aa long as the SAME OPERTATION are INVOKED with the SAME ARGUMENTS, ?? 
            -> it does NOT CHANGE the program's RESULTS at all.
        -> DATAFLOW CONCURRENCY GIVE MOST OF THE ADVANTAGES OF CONCURRENCY without the complexities that are usually associated with it. 

### 11. Explicit State
    ...

### 12. Objects 
    ...

### 13. Classes
    ...

### 14. Nondeterminism and time
    ...

### 15. Atomicity 
    ...

### 16. Where to we go from here ? 
    ...
        
