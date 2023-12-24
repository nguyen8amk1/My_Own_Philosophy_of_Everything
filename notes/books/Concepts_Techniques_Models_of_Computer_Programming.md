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
NOTE: **These knowledge applies to the Mozarts Programming system

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
        -> REFER: the IDENTIFIER to the new STORE VARIABLE

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
    ...

### 5. Correctness
    ...
### 6. Complexicty
    ...
### 7. Lazy evaluation
    ...
### 8. Higher-order Programming
    ...
### 9. Concurrency 
    ...
### 10. Dataflow
    ...
### 11. Explicit state
    ...
### 12. Objects 
    ...
### 13. Classes
    ...
### 14. Nondeterminism and time
    ...
### 15. Atomicity 
    ...
        
