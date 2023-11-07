# COMPUTATIONAL THINKING
notes from book: Computational Thinking, A beginner's guide to problem solving and programming

## GLOSSARY 
    Abstraction: 
        Way of EXPRESSING an IDEA in a SPECIFIC context 
        while at the same time SUPRESSING DETAILS irrelevant in that context.
    Algorithm: 
        A sequence of CLEARLY DEFINED STEPS:
            that describe a process to follow a FINITE set 
            of UNAMBIGIUOS instructions
            with CLEAR:
                + START point
                + END point

    Assignment: 
        process of: SETTING VALUE of a variable 

    Implication: 
        RELATIONSHIP between LOGICAL STATEMENTS
            that tells us the SECOND logically FOLLOWS from the FIRST 

    Biconditional: 
        RELATIONSHIP between logical statements 
        that tells us: 
            + the 2nd logically FOLLOWS from the 1st 
            + the 1st logically FOLLOWS from the 2nd 


    Cardinality (luc luong):
        PROPERTY describing the NUMBER OF ELEMENTS in something

    Truth value: 
        PROPERTY of a logical statement that: 
            DENOTES whether it is TRUE or FALSE
            
    Conditional:
        PROGRAMMING CONSTRUCT that:
            + ALTERS the FLOW of execution (DEPEND on the TRUTH VALUE of a condition)

    Conjunction (aka logical AND):
        Operation that:
            + CONNECTS 2 logical statements 
            + IDENTIFIES whether BOTH are TRUE 

    Disjunction (aka logical OR): 
        Operation that:
            + CONNECTS 2 logical statements 
            + IDENTIFIES whether ONE or BOTH are true

    Proposition: 
        STATEMENT that has a TRUE or FALSE value 

    Negation: 
        Operation applied to a PROPOSITION:
            that INVERTS its value.

    Premise: 
        Proposition used by an arguments.

    Deductive reasoning: 
        Applying a CHAIN OF REASONING whose: 
            CONCLUSION follows from its PREMISES

        -> GENERAL premises to form a SPECIFIC conclusions
        From General
        To Specific 
        -> Use to: Establish logical relationship

        vd: 
        Premise 1: All men are mortal.
        Premise 2: Socrates is a man.
        Conclusion: Therefore, Socrates is mortal.

    Inductive reasoning: 
        Applying a CHAIN OF REASONING whose: 
            CONCLUSION follows as a MEASURE OF PROBABILITY from its premises

        -> SPECIFIC premises to form a GENERAL conclusions 

        From Specific premises (vd: Observation)
        to General Conclusion (with some degree of uncertainty, measure of probability)

        -> Used to: MAKE GENERALIZATIONS, predictions, and inferences BASED ON OBSERVED EVIDENCE

        vd: 
        Observation 1: Every swan I've seen is white.
        Observation 2: Every swan I've read about is white.
        Conclusion: Therefore, I assume that all swans are white (but there's always a possibility of encountering a non-white swan).


    Function signature: 
        A function identifier made up of: 
            + function's name
            + ordered list of parameters its accept 

    Signature: 
        -> function signature 

    Heuristic: 
        Problem-solving technique that: 
            yields(produce) a SUB-OPTIMAL(not the best) SOLUTION judged to be SUFFICIENT
            -> not the best but sufficient -> "good enough"
    Mutable: 
        OBJECT whose: 
            VALUES can be MODIFIED after creation

    Immutable: 
        inverse of mutable


    Information Hiding: 
        CONCEALING the STRUCTURE of some PARTS (probably unstable part, part that implementation might get changes)
        behind a stable interface
        -> Hide the UNSTABLE parts behind a STABLE interface

    Subroutine: 
        CALLABLE sequence of program instructions
        PACKAGED as a DISTINCT unit 

    Library: 
        COLLECTION of: 
            + data 
            + routines 
            HIDDEN behind an INTERFACE 
        -> intended for USE BY OTHER programs 

    Loop: 
        Sequence of statements that EXECUTE potentially NUMEROUS TIMES in succession
    
    Parameter:
        Value passed to a function

    Pixel: 
        Smallest ADDRESSABLE UNIT on a computer screen 

    Script:
        EXECUTABLE PROGRAM, usually SMALL (<= few thousand lines), INTERPRETED (not compiled)

    Tree(structure): 
        Hierarchical data structure where: 
            each node:
                may have ANY NUMBER of CHILD NODES
                BUT ONLY ONE parent node 
                -> n child, 1 parent 
            the root node not have parent 

## Introduction: 
    the book teaches: 
        How to: 
            + PICK out the ESSENTIAL DETAILS of a problem
            + FORMULATE a PROBLEM in ways a computer can understand 
            + follow a PROBLEM-SOLVING PROCESS in ways that the process can be automated.

## Part 1: COMPUTATIONAL THINKING
1. What is computational thinking ? 
    Definition in a usual sense: 
        -> creating a LIST OF CONDITIONS that something must meet before considered a match 

    Computational thinking is hard to condense a rigoruous definition 
        every one have a different meaning of CT (check page 8)

    My favourite definition:   
        CT is the THOUGHT PROCESSES
        involved in FORMULATING a PROBLEM 
        and EXPRESSING its SOLUTION 
        in such a way that a COMPUTER can effectively CARRY OUT 
        (Wing, 2014)

    Divide into 2 categories: 
        + Core concepts: 
            + logical thinking
            + algorithmic thinking
            + decomposition
            + GENERALISATION and PATTERN RECOGNITION 
            + modeling 
            + abstraction
            + evaluation

        + Peripheral(ngoai vi) concepts: 
            + data representation 
            + critical thinking
            + computer science 
            + automation
            + simulation/visualization

2. Computational thinking is not: 
    Computer Science 
        -> it's not completely attached to Computer science 

    CT teaches:
        an APPROACH to PROBLEM-SOLVING 
        where the ULTIMATE AIM is to 
        PROVIDE a SOLUTION 
        whose form means it is ready to PROGRAMMED INTO A COMPUTER 

    CT takes: 
        a relatively small SUBSET of CONCEPTS (from CS)
        use them to CONSTRUCT a WIDELY APPLICABLE, problem-solving APPROACH

## Computational thinking is all about:
    APPROACH to PROBLEM-SOLVING 
    involves USING a SET of PRACTICES and PRINCIPLES from computer science 
    to FORMULATE A SOLUTION 
    that EXECUTABLE BY A COMPUTER 
