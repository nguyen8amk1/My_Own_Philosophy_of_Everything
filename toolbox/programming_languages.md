# Programming languages 
Answer these questions:
    + What is the TYPING MODEL?: 
    + What is the PROGRAMMING MODEL?: 
    + What is the reason it created? (Optional): 
    + How will you INTERACT with it?: 
    + What are the:
        + decision constructs: 
        + core data structures: 
    + What are the CORE FEATURES that make the language UNIQUE ? 

## Ruby: 
    + What is the PROGRAMMING MODEL?: 
        Pure Object Oriented -> Everything down to a single number is an object 
        unlike Java -> numbers are primitives (don't have properties and methods) -> mixed with procedural 

    + What is the TYPING MODEL?: 
        dynamic-typing: type-checking at run-time
        strongly-typed (not exactly but it behave like one most of the type )
            -> it does checking type when does operations
            vd: 4.0 + "ditme" -> can't do this, since they're different types 

        Duck-typing

        -> the TRADE-OFF that developer have to deal with: 
            cons: 
                + can't catch as many errors as static typing  
            pros: 
                + Duck-typing: your class DON'T have to inherit from the SAME PARENT 
                to be USED THE SAME WAY 
                    -> Extremely important when comes to CLEAN OBJECT ORIENTED DESIGN
                    An important mindset in design philosophy is: 
                        code to INTERFACES rather than IMPLEMENTATIONS (@Confuse)
                        -> Duck-typing support very good
                            -> if an object has PUSH and POP methods -> it can be treated as a STACK 

        -> the WAY TO ATTACK THE PROBLEM: 
            ....
        -> the WAY THE LANGUAGE WORKS: 
            ....

    + What is the reason it created? (Optional): 
        ....

    + How will you INTERACT with it?: 
        Using interpreter 

    + What are the:
        + decision constructs: 
            ....

        + core data structures: 
            + array:
            + hash: 
            with multiple APIs sit on top

    + What are the CORE FEATURES that make the language UNIQUE ? 
        Mixin: 
            -> 2 way dependencies (Child and Parents both depends on each others methods)
            -> while inheritance is just 1 way dependencies (Child depends on Parent methods)

        Meta-programming: 
            Open class:
                can add/change definition of any class at any time
                    -> building languages to encode your own DOMAIN
                    -> vd: express all number as inches, ... 

            Method missing: 
                when a method is not found in a class 
                -> method_missing method will be called for debugging purposes
                but if we overwrite (Open Class) that parts to ultilize it to do something else
                    vd: use the not found method name as a parameter to some other purposes 
                        -> WE WILL GET INFINITE AMOUNT OF METHODS WITHOUT WRITING ANY MORE CODE   
                        vd: Roman.II methods
                                can spit out value 2 
                            Roman.III methods 
                                can spit out value 3 
                            even though the II and III methods not exist
                            THE LOGIC OF CONVERSION IS IN THE METHOD_MISSING BODY

            Module: 



            -> 
