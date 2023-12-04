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

    Reasoning: 
        thinking about something in a logical way 

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

## Logical and Algorithmic Thinking: 
    LOGIC and ALGORITHMS are ESSENTIAL to CT 
    each has it's own SET of:
        + rules
        + procedures
        + definitions
        -> very PRECISE and SYSTEMATIC 
    -> CAN'T RELY solely on your INTUITION 
        when dealing with these topics

    -> Overcome by learn the precise, difficult core concepts 
    -> In this book: 
        FOCUS on FEW CORES ELEMENTS 
            -> learned how to apply logic and algorithms to problem-solving 

    Logical thinking:  
        Argument: a CHAIN of REASONING that
                  ends up in a CONCLUSION

        Logic: a SYSTEM 
        used for DISTINGUISHING between 
        correct and incorrect ARGUMENTS
            -> includes:
                + a SET of PRINCIPLES that
                when APPLY to ARGUMENTS
                -> determine what is TRUE 

        Applying logic:  
            in a sense, is a way of DEVELOPING and TESTING a HYPOTHESIS.
            assumes you ALREADY KNOW at least SOME THING FOR SURE 
            allows you to USE that KNOWLEDGE to arrive some FURTHER CONCLUSIONS.

        In logical argument: 
            -> Premise: THING YOU ALREADY KNOW 
                -> basically a STATEMENT that can be evaluate to obtain an answer of "true" or "false"
                -> Condition: have TRUTH VALUE 

            -> Once ALL PREMISES ARE STATED 
                -> next step: ANALYSE them -> form CONCLUSION 

        Inductive and Deductive arguments:  
            IMPORTANT to realise: 
                -> some logical arguments are stronger than others 
                -> CATEGORISE arguments based on their CERTAINTY:
                    -> 
                    + DEDUCTIVE: 
                        is the strongest form of reasoning 
                        conclusion follows its premises
                        -> very strict standard 
                        -> hard to construct 
                        an argument can fail in 2 ways: 
                            + one of the PREMISES is FALSE (vd: all dog are brown) 
                                -> garbage in, garbage out (premises wrong, conclusion wrong)
                            + faulty logic (The CONCLUSION does NOT FOLLOWS from PREMISES)
                                vd: Alls A are B
                                    C is B 
                                    -> C is a A
                        -> In real life: Deductive argument are relatively RARE
                            Real world problems usually give patchy, messy knowledge 
                            rather than nice and clean 
                            -> can't use Deductive argument with that

                    + INDUCTIVE:
                        Deals with:
                            PROBABILITY 
                            rather than 
                            hard BLACK and WHITE rules.  

                        The premises of inductive arguments are NOT UNQUESTIONABLY TRUE
                        but rather HAVE SOME AMOUNT OF CONFIDENCE IN THEM 
                        -> The CONCLUSION is NOT GUARANTEE to be TRUE
                        -> But rather a TRUST WORTHY conclusion
                        
                        vd: A bag contains:
                            + 99 red balls 
                            + 1 black ball 
                            100 people each drew 1 ball from the bag 
                            Sarah is one of those people 
                            -> Sarah PROBABLY drew a red ball 
                        -> Perfectly fine 
                            -> (as long as you ACKNOWLEDGE the aspect of PROBABILITY involved)

                        IMPORTANT: The ANSWER of the computer is only 
                        as RELIABLE as its REASONING (your reasoning)

                        -> Your RESPONSIBILITY to MAKE SURE: 
                            + the reasoning is valid 
                            + give computer RELIABLE INPUT 
                            + Know how to INTERPRET the Computer's CONCLUSION 
                                + completely true (the reasoning was deductive)
                                + probably true (the reasoning was inductive)

        Boolean Logic: 
            Much of our reasoning is INDUCTIVE 
            but computers are NOT WELL equipped to DEAL with SHADE OF GREY (probabilities)
            Computers are more apt to DEAL with BLACK and WHITE ISSUEs 
            -> Need: a SYSTEM OF LOGIC that deal with black and white issues 
                -> Boolean logic 

            Propositions: 
                -> STATEMENT in Boolean Logic 
                Properties: 
                    + only have 1 VALUE at any moment
                        -> there is no grey value 
                        -> MAPPING those GREY values to either BLACK and WHITE 

                    + must have CLEAR and UNAMBIGUOUS MEANING 
                        -> vd: moving fast (fast is ambiguous)
                            -> need more clear meaning -> vd: fast means traveling speed > 70mph

                    + possible to COMBINE individual propositions to make more complex ones 
                        (COMPOUND PROPOSITIONS)
                        vd: Jenny is wearing the shirt
                            and 
                            The shirt is red  
                        -> Helpful because we often want to EVALUATE SEVERAL STATEMENTS 
                            before reaching a conclusion 
                        -> CONNECTING single propositions together using LOGICAL OPERATORS 

            Logical operators:  
                -> CONNECT SINGLE PROPOSITIONS together to create a compound proposition 
                NOTES: 
                    they have SPECIFIC MEANING in logic 
                    that occasionally RUN COUNTER to our INTUITIVE UNDERSTANDING.

                + AND (technical name: CONJUNCTION)
                    -> CHAINS propositions together in a way that 
                        ALL of them must be TRUE 
                        or ELSE the conclusion will be FALSE

                + OR (technical name: DISJUNCTION)
                    -> CHAINS propositions together in a way that 
                        AT LEAST ONE of them must be TRUE 
                        or ELSE the conclusion will be FALSE

                + NOT (techical name: NEGATION)
                    -> modifies a single proposition (FLIP the truth value of the propositions)
                    NOT CHAIN multiple propositions. 

                    NOTES: 
                        sometime negation MAKE IT EASIER to express the chain of REASONING  

                + IMPLIES (technical name: IMPLICATION)
                    -> State that there is a CORRELATION between TWO STATEMENTS
                        -> If A is true -> B is also true 

                    NOTES: 
                        CORRELATION is NOT CAUSATION
                            -> CAN'T not work backward (B can't determine A)

                + IF AND ONLY IF (technical name: BICONDITIONAL)
                    second prositions is influenced solely by the first
                    If A is true -> B is true 
                    If A is false -> B is false 
                    No exception

                    NOTES:  CAN work backward 

            Symbolic Logic:  
                To eliminate ambiguity 
                The meaning of each logical operator is specified in PRECISE mathematical detail.
                    -> Truth table 

                IMPORTANT: Venn diagram for operators: 
                    page 22, 23, 34 

        Algorithmic Thinking: 
            NOTES: 
                LOGIC and ALGORITHM is NOT THE SAME 
                Algorithms build on logic 
                    because their work are:
                        + MAKE logical DECISIONS
                        + STICHING those DECISIONS together

                Logic GIVES a SET of RULES that 
                ALLOW you to REASON about some aspect of the WORLD.   

                Algorithms:
                    + INTERGRATE all of these rules 
                    + EXECUTE actions based on the CONCLUSIONs of the Logic Rules

            Algorithms are a way of SPECIFYING a MULTI-STEP task 

            PROPERTIES of algorithms: 
                + Collection of individual steps:
                + Definiteness
                    -> every step must have precise meaning (only 1 meaning)
                + Sequential
                    -> the steps must be CARRIED OUT IN the ORDER specified 
                    -> Why sequential was so important: 
                        It's all about STATE
                        STATE: 
                            the CURRENT CONFIGURATION of ALL THE INFORMATIONS 
                            kept track of by a program/algorithm in one instant of time 
                            -> CLEARLY SEQUENCING the steps ENSURES that 
                            all STATE ALWAYS CHANGES in the SAME WAY whenever the algorithm is executed

            IMPORTANT: 
                there is NO "GLOBAL VIEW" when it comes to algorithms
                    at EACH INSTANT IN TIME
                    the ENVIRONMENT in which the algorithm is being run EXISTS IN SOME PARTICULAR STATE 
                    -> Basically exist as a SERIES of SNAPSHOT 
                    -> The computer FORGETS about PREVIOUS SNAPSHOT 
                    -> Need a WAY TO REMEMBERING things that happens in PREVIOUS SNAPSHOT
                        -> VARIABLES
                    Math Variables:
                        used in function to REPRESENTS a QUANTITIES that VARY.
                    Algorithm Variables: 
                        SCRATCHPAD that used as a PLACEHOLDER for IMPORTANT INFORMATION the computer should keep note of 

            CONTROLLING algorithm EXECUTION: 
                2 ways of control the execution of algorithm using VARIABLES: 
                    + Iteration (Loop): 
                        Variable in loop: 
                            the thing that CHANGES from ONE LOOP to the NEXT

                    + Selection (Conditional): 
                        1. Test a VARIABLE current VALUE 
                        2. MAKE a DECISION based on it 
                        -> Creating a POINT at which the computer has to DECIDE 
                            between: 
                                + performing a set of steps or not 
                        -> ENCAPSULATE the INFORMATION needed to MAKE that DECISION.

## PROBLEM-SOLVING AND DECOMPOSITION: 
### Problem solving is partly a CREATIVE PROCESS.
    -> it can not be totally systematised 
    -> BUT:
        + strategies 
        + heuristics(kinh nghiem) 
        + good practices 

        exists to help 

### Systematic approach: 
    First proposed by Polya in the book "How to solve it"
    steps: 
        1. Understand the problem 
        2. Devise a plan 
        3. Execute the plan 
        4. Review and extend

    -> We FOCUS on the FIRST 2 STEPS: 

### Don't panic: 
    the:
        + Size 
        + Complexity 
        + Huge number of Unknowns
        -> can frustate your attempts to start 

    few HINTS to help starting: 
        + "don't be put off by perceived size and complexity"
            Big problems are RARELY a SOLID MONOLITH BLOCK 
                -> they are a GROUP of SMALL, INTERRELATED PROBLEMS
            -> The tricks is: 
                to PICK THEM APART and REDUCE a big problem into a:
                    + smaller 
                    + simpler 
                    + more manageable ones 

        + "resist the urge to jump straight into writing a solution"
            -> if you jump straight to writing solution 
                your solution will only solve a very specific version of the problem (not so good)

### DEFINING the problem  
    The hardest part of problem solving: 
        is CHARACTERISING THE PROBLEM. 

    Problem solving involves: 
        TRANSFORMING an UNDESIRABLE state of affairs (tinh huong)- the STARTING POINT
        INTO an desirable state of affairs - the GOAL
        -> the STARTING POINT and the GOAL are INTIMATELY LINKED 

    EXAMINING the starting point: 
        -> NAIL DOWN exactly: 
            + WHAT is undesirable 
            + WHY  

    "It's foolish to answer question that you do not understand"
    -> advice: 
        + try RESTATING the problem in YOUR OWN WORDS 
        + represent the problem using PICTURES and DIAGRAMS 
        + There will be: 
            + knowns 
            + unknowns 
            at the start
            -> should make sure that enough information is known to form a solution.  
            if there isn't -> MAKE THE UNKNOWNS EXPLICIT. 
            
    KEYPOINTS: 
        + the goal defines: 
            WHAT need to be done
            NOT HOW it should be done. 

        FOCUS on WHAT YOUR GOAL LOOKS LIKE. 
        -> Describing how a working solution should look
        MAKE SURE: 
            + clear 
            + specific 

        IF the goal is COMPLICATED 
            -> DESCRIBE the DESIRED FEATURES of the solutions.
            -> Write a specification.

### DEVISING(nghi ra) a solution: 
    Once you have: 
        + a finished problem DEFINITION complete with GOAL
            -> it's time to find the strategy or a solution 

    There are multiple solutions.
        some good, some terrible 
        -> SHOULD FOCUS ON FINDING THE BEST SOLUTION YOU CAN.

    Quality: 
        INDIVIDUAL PARTS of a problem CAN found the PERFECT SOLUTIONS.
        But the OVERALL SOLUTION CAN'T BE PERFECT since the trade-offs between competing part always happens.

    Iteration:     
        Take an ITERATIVE APPROACH instead of trying to solve everything in one swoop   
        -> go back and improve the current solution 

        HOW MANY STEPS to repeat DEPENDS ON: 
            the solution SHORT-COMINGS

### DECOMPOSITION
    HEURISTIC problem solving technique: 
        vd: trial and error, rule of thumb, drawing an analogy 
        -> Decomposition

    Is a DIVIDE AND CONQUER strategy 
        -> use when: 
            problem TOO LARGE or COMPLEX to deal with ALL AT ONCE 

    -> Apply Decomposition = PICK ALL THE STEPS APART 

    Decomposition normally (recursively) BREAKS all the STEPS down into a TREE-STRUCTURE 

    TREE can represent a huge range of DIFFERENT STRUCTURES @NeedInvestigation ?? 

    **AVOID: 
        Getting bogged down in the details of: HOW TO SOLVE THE SUB-PROBLEMS. 
            -> At this stage -> just focus on WHAT TO DO, not HOW TO DO IT 

    NOTE: 
        Decomposition WON'T result in: A COMPLETE PLAN OF ACTION 
        But:
            + it can give you a STARTING POINT for FORMULATING one.

        It can SHOWS: INDIVIDUAL TASKS  
        But it DOESN'T SHOW: the ORDER in which to TACKLE them 
        But the RELATIONSHIP between the sub-problems is APPARENT. 

### OTHER EFFECTIVE STRATEGIES
    -> These are some of the most useful strategies, 
    it may not work all the time, but they are very useful.

#### Think critically 
    "ALL KEY DECISIONS SHOULD HAVE A GOOD REASON BEHIND THEM" 

     + VALIDATING IDEA (1): 
        vd: Design a layout of a bookshop
            Initial question:
                -> Have i chosen the RIGHT STRUCTURE for laying out the books on the shelf ? 
                -> NOT CLEAR what "right structure" actually mean  
                -> LOOK AT YOUR GOAL TO CLARITY IT (2)
                -> vd: Goal: 
                    + (pros) QUICK and EASY for ADDING NEW BOOK to the shelf.
                        -> the structure could be: UNORDERED
                        cons: the CUSTOMER have to MANUALLY BROWSE the book 

                    + (pros) Easy to LOCATE a SPECIFIC BOOK. 
                        ->  the structure could be: ORDERED in some order (alphabetically, author, ...)
                        cons: the OWNER have to SPEND TIME SORTING the books.
    
     + EXPOSE ASSUMPTION to the ideas (very important): (3)
        -> ASSUMPTIONS made IMPLICITLY COULD well turn out to be FALSE.

        vd:  
            Deciding: books need to be sorted 
                -> ASSUMES that the bookshop OWNER CAN AFFORD to put the TIME REQUIRED for it
                -> RAISE THE QUESTIONS: is that ASSUMPTION JUSTIFIED ? (4)
                    -> It may turn out that you need ANOTHER SOLUTION or get MORE EMPLOYEES for that job

        NOTE: 
            For any system you put in place -> Always ask the questions: 
            -> "WHAT IF IT GOES WRONG" (5) 
            vd: For the bookshop scenario, you might ask: 
                -> What if the book is NOT IN THE CORRECT PLACE on the shelf.  

            -> Your RESPONSE can vary: (6)
                + IMPROVE the solution 
                + ELEMINATe the possibility of that problem occur 
                + put a PLAN in place to EXECUTE when the problem occur.


#### Solve a CONCRETE instance 
    ...

#### Find a RELATED PROBLEM
    ... 

#### Work backwards (top down)
    ...  

### PATTERN and GENERALIZATION
    ...
