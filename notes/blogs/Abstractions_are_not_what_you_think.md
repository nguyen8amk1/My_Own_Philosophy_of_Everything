# Abstraction: Not What You Think It Is
notes from this blog: https://www.pathsensitive.com/2022/03/abstraction-not-what-you-think-it-is.html

A lot of definition of Abstraction are from: 
    ACCUMULATED INTUITION over decades.
    -> they can't state a formal definition

basic definition: 
    make code more understandable by HIDING DETAILS 
    -> but abstraction often get MISUSED and actually make things HARDER TO UNDERSTAND 

Blog GOALS: 
    1. Provide specific NAMES for CONCEPTS that often get grouped under the term "Abstraction"
        -> reduce contradiction between people with different concepts in their head
    2. Provide formal definition of "Abstraction" in the context of software (with concrete examples)

    once you learn how to actually write down an ABSTRACTION MAPPING, 
    you gain the ability to look beyond the binary 
    and EXPLAIN THE EXACT BENEFIT THAT a given abstraction DOES or DOES NOT provide a REASONER

# NOT ABSTRACTION: 
    Functions: 
        In lambda-calculus: 
            the abstraction is the act of creating a function 
            but create a function in the meaning of: 
                converting a normal expression: (vd: x + 1) into lambda calculus expression (vd: lambdax.x+1)
                    -> abstraction x + 1 into lambda.x+1
            NOT in the meaning of: 
                seeing 2 equation have the same structure -> abstract them into a function

        -> Abstract = Convert/Translate not PATTERN GROUPING( this act is called Anti-Unification)
            -> ADDING CURLY BRACES around things that already in place
        -> The term: "Abstract things into functions" most of the time get the WRONG MEANING 

    Anti-Unification: 
        ->  taking two things that are mostly similar, and REPLACING THE DIFFERENT PARTS WITH VARIABLES
            -> DON'T REPEAT YOURSELF 

    Boxing: 
        Having too much Anti-Unification 
        -> The result is a function with the same name but do things differently with different input 
        -> You don't know what the actual purpose of the function  
        -> You CAN'T simply IGNORE THE DETAILS and just start using it -> not abstraction 

    Indirection:
        indirection typically means:
            "any time you need to jump to another file or function to see what's going on."
        It commonly takes the form of (layers of abstraction):
            + long chains of SINGLE-LINE FUNCTIONS calling each other 
            + class definitions SPLIT Into a hierarchy across 7 files.

    Interfaces, Typeclasses, and Parametric Polymorphism: 
        These 3 are MECHANISMS for:
            GROUPING MULTIPLE function IMPLEMENTATIONS 
            so that a SINGLE INVOCATION may DISPATCH to any of them.
        Typeclasses, a.k.a. “traits,”:
            -> are essentially INTERFACES NOT ATTACHED TO OBJECTS. 
        Parametric polymorphism, a.k.a. “generics,”:
            ->  COMBINE FUNCTIONS which DIFFER IN NOTHING BUT their TYPE SIGNATURE.
            -> essentially just adding an extra parameter (type parameter) to a function

# TRUE ABSTRACTION: 
    -> MAPPINGS between a COMPLEX CONCRETE WORLD and a SIMPLE IDEALIZED WORLD
    -> In essence:
        abstractions help CREATE A HIGHER LEVEL OF UNDERSTANDING 
        where precise operations and reasoning can occur, 
        DESPITE the INHERENT COMPLEXITY of the underlying concrete systems or data structures.

    vd:
        the number 42 can be represented in many forms, such as with 
            + bits, 
            + tally marks, 
            + and even (as is actually done in mathematics) as a set. 

    IN GOOD ABSTRACTIONS, 
        YOU'LL NEVER THINK THAT IT'S EVEN AN ABSTRACTION.

    So, what do abstractions actually look like in code?
        They don't.

    Where are the abstractions?: 
        based on abstract interpretation (something about: "bisimulation"): 
            Abstractions 
                are MAPPING: 
                a pattern we IMPOSE on the WORLD, NOT the ENTIIES it relates
                    the worlds are called: Abstract domain and Concrete domain
                -> instead of asking: "Is Y an ABSTRACTION OF X"
                    -> ask:  "Is there an ABSTRACTION FROM X TO Y?
                    -> MAPPING = FROM X TO Y 
                EXIST INDEPENDENTLY OF THE SYSTEM'S INTERNAL WORKINGS
                    but the MAPPING is still CONCRETE 

            have 2 properties: 
                + soundness (chac chan):  
                    “commutative diagram” in that ANY PATH through the diagram obtains the SAME RESULT
                    vd: 
                        given an input set of voltages, it would be equivalent to either 
                            (a) run a circuit for adding one and then convert the resulting voltages to a number
                            (b) convert the voltages to a number and then add 1 with pen-and-paper. 

                + precision: 
                    Adding 1 to a number produces exactly one result, 
                    even though it corresponds to a diverse set of output voltages.

                    -> Wait?? -> Why it sounds so much like Functors :v 

                    ....Not done 

## Conclusion: 
    Concrete domain: 
        -> real-world/detailed representation of a:
            + system
            + data
            + state  

    Abstract domain: 
        -> simplified, high-level view of the system, 
        FOCUSED on ESSENTIAL FEATURES while omitting unnessesary details.

    Abstraction: 
        is a MAPPING:
            + from: concrete domain
            + to: abstract domain

    instead of asking: 
        abstract from a to b:   
        then ask: 
            which OPERATIONS can be TRACKED precisely with reference only to the abstract domain.

        -> What OPERATIONS can the ABSTRACTED REPRESENTATION CAN DO ? 

        -> If the operations of the abstracted presentation executed with high degree of accuracy compare to the concrete desire -> the abstraction is precise   