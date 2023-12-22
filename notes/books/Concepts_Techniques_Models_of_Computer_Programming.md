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
    + MAIN GOAL: 
        Teaching programming as a UNIFIED DISCIPLINE with a SCIENTIFIC FOUNDATION. 

    + Programming: 
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
