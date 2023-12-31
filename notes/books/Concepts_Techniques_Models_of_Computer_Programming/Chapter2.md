# CHAPTER 2: DECLARATIVE COMPUTATION MODEL 

## PROGRAMMING ENCOMPASSES 3 THINGS: 
    1. a COMPUTATION model: 
        -> a formal system that defines: 
            + a language 
            + how SENTENCES of the LANGUAGE (vd: expresssion, statements, ...) 
                are EXECUTED by an ABSTRACT MACHINE 

    2. a SET of:
            + PROGRAMMING TECHNIQUES 
            + DESIGN PRINCIPLES 
            used to WRITE PROGRAMS in the LANGUAGE OF THE COMPUTATION MODEL.  

        or another name: 
            Programming model = a set of <the above> 
        NOTE: 
            A PROGRAMMING model is always BUILT ON TOP of a COMPUTATION model. 

    3. a SET of REASONING TECHNIQUES 
        -> let you REASON ABOUT PROGRAMS  
            -> increase CONFIDENCE that they BEHAVE CORRECTLY
            -> calculate program's EFFICIENCY

## WHAT IS A REASONABLE COMPUTATION MODEL ? 
    -> one that:
        + CAN be used to SOLVE MANY PROBLEMS 
        + has STRAIGHTFORWARD, PRACTICAL - REASONING TECHNIQUES
        + CAN be IMPLEMENTED EFFICIENCLY

    Simplest Computation Model: 
        -> DECLARATIVE PROGRAMMING

    **DECLARATIVE PROGRAMMING: evaluating FUNCTIONS over PARTIAL DATA STRUCTURE ?? 
        -> STATELESS programming

        + Encompasses, core ideas of 2 main DECLARATIVE PARADIGM: 
            + FUNCTIONAL programming
                -> programming with FUNCTIONS over COMPLETE VALUES ?? 
            + LOGIC programming
                -> deterministic logic programming

        -> DP can be made concurrent without losing DP good properties 

    We will later enrich the model with new concepts 
    -> Some of the MOST IMPORTANT CONCEPTS are:
        + Exception handling 
        + Concurrency: 
            + Dataflow 
            + Lazy execution 
            + Message passing
            + Active objects
            + Monitors 
            + Transactions
        + Components
        + Capabilities (for ENCAPSULATION, SECURITY)
        + State (leading to OBJECTS and CLASSES)

    NOTE: 
        **IMPERATIVE PROGRAMMING: 
            -> STATEFUL programming
        **DECLARATIVE PROGRAMMING: is a COMPUTATION MODEL


## STRUCTURE OF CHAPTER 2
    8 sections: 
    + 2.1: 
        -> Explains: 
            + How to define:
                + Syntax 
                    -> defined by: context-free grammar + language constraints
                + Semantics 
                    -> defined in 2 steps: 
                        + translate - practical language -> kernel language
                        + give semantics - of kernel language 
                of pratical programming languages

                -> Use Syntax and Semantics to DEFINE all the COMPUTAION MODEL 

    + 2.2, 2.3, 2.4: 
        -> Define the SYNTAX and SEMANTICS of Declarative model 
        + 2.2: 
            -> gives the DATA STRUCTURES: 
                + single-assignment store, and its content
                + partial values
                + dataflow variables 
        + 2.3: 
            -> define KERNEL LANGUAGE SYNTAX
        + 2.4: 
            -> define KERNEL LANGUAGE SEMANTICS
            in terms of a SIMPLE ABSTRACT MACHINE

            Semantics is DESIGNED to be: 
                + Intuitive 
                + Permit STRAIGHTFORWARD REASONING about: 
                    + Correctness
                    + Complexity

    + 2.5:  
        -> Use the abstract machine to EXPLORE: 
            + memory behaviour of computations
            -> look at: 
                + last call optimization
                + memory life cycle 
    + 2.6:  
        -> DEFINES a PRATICAL PROGRAMMING LANGUAGE - ON TOP - of the KERNEL LANGUAGE 

    + 2.7:  
        -> EXTENDS declarative model with: 
            + Exception Handling 
            -> Allow programs to HANDLE: 
                + unpredictable situation
                + exception situation

    + 2.8:  
        -> advance topics 

## 2.1 - DEFINING PRATICAL PROGRAMMING LANGUAGES
    + Practical Language: 
        -> Programming languages that are used to SOLVE REAL-WORLD PROBLEMS
        -> It's like a TOOLBOX of an EXPERIENCED MECHANIC: 
            -> many DIFFERENT TOOLS for DIFFERENT PURPOSES
            -> ALL TOOLS ARE THERE FOR A REASON

### 2.1.1 Language SYNTAX     
-> DEFINES - what are the LEGAL PROGRAMS( programs that can be SUCCESSFULLY EXECUTED )

NOTE: at this stage (syntax stage), we're DO NOT CARE what the programs are actually doing 
    That is SEMANTICS (what the programs are actually doing)

#### Grammars: 
    -> SET OF RULES - DEFINES - HOW to make "SENTENCES" out of "WORDS"
    In programming: 
        Sentences = STATEMENTs
        Words = TOKENs

        -> 2 level of structures: 
            + Statements (sentence) = Sequence of tokens (words)
            + Token (word) = Sequence of characters (letters)

            **-> Sentences -> Tokens -> Characters (sort in term of level of abstractions)

    + Grammars are used for DEFINING BOTH:  
        + Statements 
        + Tokens

    Code: a sequence of characters 
        where: 
            + ' ' : space 
            + '\n' : new line 

    + TOKENIZER/lexical analyzer: 
        + input: a SEQUENCE of CHARACTERS
        + output: a SEQUENCE of TOKENS 
    
    + PARSER: 
        + input: a SEQUENCE of TOKENS
        + output: a PARSE TREE


    **Code -> Tokenizer -> Parser


#### EBNF (Extended Backus-Naur Form): 
    -> Use for DEFINING GRAMMARS 
    -> DISTINGUISHES: 
        + TERMINAL symbols 
            -> a token 

        + NONTERMINAL symbols 
            -> a sequence of tokens
            -> is DEFINED by means of GRAMMAR RULES 

            + Grammar rules: 
                -> shows HOW to EXPAND into TOKENS 
                    vd: 
                    <digit> ::= 0|1|2|3|4|5|6|7|8|9
                    -> meaning: <digit> presents one of the ten tokens 0,1,...9 

                -> can refer to other nonterminals as well 
                    vd: 
                    <int> ::= <digit> {<digit>}
                    -> meaning: an integer is a digit followed by any number of digits 
                -> Use to:
                    + VERIFY a STATEMENT is legal 
                    + GENERATE STATEMENTS 
                        -> process of CREATING such VALID SEQUENCES based on the grammar rules

#### How to read grammar: 
    steps: 
        1. Start with: NONTERMINAL symbols 
        2. Reading from left to right to check if the sequence of tokens match the following schemes: 
            + Each terminal symbol encountered is added to the sequence. 
            + ...
            + ... Page 33  

#### Context-FREE and Context-SENSITIVE grammars: 
    + Formal language:
        -> any WELL-DEFINED SET of STATEMENTS 
    + Techniques to DEFINE grammars can be CLASSIFIED according to HOW EXPRESSIVE THEY ARE
        vd: What KIND OF LANGUAGES they can GENERATE. 

    + Context-FREE grammars: 
        -> the EXPANSION of nonterminal is ALWAYS THE SAME, no matter where it is used. 

    + Context-SENSITIVE grammars: 
        -> a grammar that contains a NONTERMINAL WHOSE USE DEPENDS ON THE CONTEXT where it is used 
        vd: 
            you can only print a variable if the variable was already defined. 

    -> Practical Programming Languages DEFINED in 2 PARTS: 
        + Context-free Grammar
            -> easy to: 
                + understand
                + read

            -> has LOCALITY property: 
                -> a nonterminal symbol can be understood 
                by examining ONLY THE RULES NEEDED TO DEFINE IT 
                -> the RULES that USE it can be IGNORED

                vd: to understand <digit> 
                    -> EXAMINE: 
                        <digit> ::= 0|1|2|3|4|5|6|7|8|9
                    -> IGNORE: 
                        <int> ::= <digit> {<digit>}

        + Set of extra conditions
            -> Corrected the Context-free grammar
            by imposing a set of extra conditions
            vd: declare-before-use restriction

        -> Context-SENSITIVE Grammar = Context-free Grammar + Set of extra conditions

#### Ambiguity: 
    ... 

#### Syntax notation used in the book: 
    ... 






### 2.1.2 Language SEMANTICS     
    ... 

#### The Kernel language approach: 
    ... 

#### Formal semantics: 
    ... 

#### Linguistic abstraction: 
    ... 

#### Syntactic sugar: 
    ... 

#### Language design: 
    ... 

#### Other translation approaches: 
    ... 

#### The Interpreter approach: 
    ... 