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
    Teaching programming as a UNIFIED DISCIPLINE with a SCIENTIFIC FOUNDATION. 

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
    ...
