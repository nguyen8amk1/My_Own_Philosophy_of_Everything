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
    Context-free grammars can be ambiguous 
    -> there can be several parse trees that correspond to a given token sequence. 

    -> an UNDESIRABLE PROPERTY of a GRAMMAR 
    since it's unlcear exactly what program is being written.

    vd: 
        Given these 2 grammar expression: 
            <exp> ::= <int> | <exp> <op> <exp>
            <op>  ::= +|* 

        -> Parse tree generate from the expression: 2 * 3 + 4
            + first: 
               *
              / \
             2   +
                / \
               3   4

            + second: 
                +
               / \
              *   4
             / \
            2   3

        -> Ambiguity (don't know which to choose)

    + To Remove Ambiguity: 
        + Grammar rules can be REWRITTEN
            -> BUT this can MAKE the rules more COMPLICATED.  

        + Add EXTRA CONDITTIONS (a MORE CONVENIENT approach)
            -> RESTRICT the parser 
            so that ONLY 1 PARSE TREE IS POSSIBLE.
            -> called DISAMBIGUATE the grammar.

        vd:  for expresssion such as binary operators  
            -> add 2 conditions: 
                + precedence (do uu tien)
                + associativity (tinh ket hop)

    + Precedence: 
        -> Operators with high precedence 
        are PUT as DEEP IN THE PARSE TREE as possible. 
        -> if * is deeper in the tree than + 
            -> called * BINDS TIGHTER than + 
            -> We choose the second one.

    + Associativity: 
        -> condition on an EXPRESSION with the SAME OPERATOR  
            vd: 2 - 3 - 4 
        -> Precedence is NOT ENOUGH to DISAMBIGUATE 
        because ALL OPERATORS have the SAME PRECEDENCE
        -> have to choose between 2 trees: 
            + (2 - 3) - 4
            + 2 - (3 - 4)

        + Determine whether: 
            + left most operator
            + right most operator

            BINDS TIGHTER

        -> there are 2 POSSIBLE ASSOCIATIVITY VALUE for operation - 
            + left 
                -> (2 - 3) - 4 is chosen
            + right  
                -> 2 - (3 - 4) is chosen

#### Syntax notation used in the book: 
    Each NEW DATA TYPE and LANGUAGE CONSTRUCT 
    is INTRODUCED together WITH a small SYNTAX DIAGRAM 
        -> shows HOW IT IT FITS IN THE WHOLE LANGUAGE

    + Syntax diagram: 
        -> gives GRAMMAR RULES for a simple CONTEXT-FREE GRAMMAR of tokens.  
        -> the notation SATISFY 2 PRINCIPLES: 
            + 1. All grammar rules stand on their own. 
                NOTE: 
                    NEVER give an incorrect grammar rule 
                    just to "simplify" the presentation.

            + 2. Have CLEAR INDICATION symbol to determine whether 
            a grammar rules defines: 
                + COMPLETE definition
                + PARTIAL definition

                of nonterminal symbol 
                    -> always end in "..." (meaning "SOMETHING ELSE")

        vd syntax diagram (for 2 partial definitions of two non terminals):  

            <statement>  ::= skip | <expression> '=' <expression | ... 
                -> meaning: 
                    a statement can be the keyword 'skip'
                    or two expression separated by the '=' symbol
                    or SOMETHING ELSE (the '...')
                
            <expression> ::= <variable> | <int> | ... 
            
            <statement> ::= if <expression> then <statement> 
                            { elseif <expression> then <statement> } 
                            [ else <statement> ] 
                            end | ...
                    
                + meaning: 
                    + { something }
                        -> there can be any number of occurences including ZERO
                    + [ something ]
                        -> can be occur zero or 1 time 
                

### 2.1.2 Language SEMANTICS     
    -> defines WHAT A PROGRAM DOES when it executes. 

    -> IDEALLY defined in a simple MATHEMATICAL STRUCTURE 
    that lets you REASON ABOUT THE PROGRAM, about its:
        + correctness
        + execution time
        + memory use 
        without introducing any irrelevant details. 

        -> Kernal language approach 

#### The Kernel language approach: 
    -> defines the SEMANTICS of PROGRAMMING LANGUAGES
    -> all languages are defined in terms of: 
        TRANSLATION into a CORE LANGUAGE known as the KERNEL LANGUAGE.

    + KERNEL LANGUAGE APPROACH consist of 2 parts: 
        + 1. define a VERY SIMPLE LANGUAGE (kernel language)
            -> should be easy to REASON

            Computation Model = kernel language + data structures 

        + 2. define a TRANSLATION SCHEME
            from: full programming language
            to: kernel language
            -> should be as SIMPLE as possible 

            -> 2 KINDS of translation:
                + Linguistic Abstraction
                + Syntactic sugar 

#### Formal semantics: 
    ... 

#### Linguistic abstraction: 
    Using a programming language,
    at some point we may feel the need to EXTENT THE LANGUAGE 
        -> ADD A NEW LINGUISTIC CONSTRUCT. 
    vd: 
        the declaration model has no looping constructs.  
        -> add a "for" construct to express certain kinds of loops that are useful 
        
    + Linguistic Abstraction: 
        **-> A LANGUAGE CONSTRUCT that is both: 
            + abstraction
            + addition 
            to the language syntax 

    + Define an Linguistic abstraction: 
        -> 2 phases: 
            + 1. Define a NEW GRAMMATICAL CONSTRUCT 
            + 2. Define the new construct's TRANSLATION into the kernel language

    vd: 
        FUNCTION is a Linguistic abstraction 
            with keyword "fun"
        but the kernel language (of this chapter) only has PROCEDURES
            -> but function are so useful that we added it as a Linguistic Abstraction

    The TRANSLATION - MAKES IT CLEAR WHAT THE SEMANTICS IS 

    Useful for:  
        + 1. Improve properties of a language such as:
                + expressiveness
                + correctness
                + security 
                + efficiency
        + 2. Hiding the abstraction's implementation from the programmer
            -> makes it impossible to use the abstraction in the wrong way
            -> the compiler can use this information to give more efficieny code. 

     -> Have broad impact on the language, 
        AFFECTING how developers THINK about and USE the language   

#### Syntactic sugar: 
    -> Shortcut notation for frequently occuring idioms
        -> is part of the language syntax
        -> DEFINED BY GRAMMAR RULES 

    + Syntactic sugar vs Linguistic Abstraction: 
        + Similarity: 
            -> both providing a more user-friendly/expressive way of writing code. 
        
        + Differences: 
           + Syntactic sugar:  
                -> CONVENIENT WAY to express certain constructs
                    -> doesn't introduce new functionality
                    -> can be precisely MAPPED to the UNDERLYING, more explicit language CONSTRUCTS
                    -> DOESN'T BRING NEW ABSTRACTIONS 

                vd: 
                    // Syntactic Sugar (List Comprehension)
                        squares = [x**2 for x in range(10)]

                    // Equivalent Full Language
                        squares = []
                        for x in range(10):
                            squares.append(x**2)

                + Define: 
                    -> DEFINED BY GRAMMAR RULES 

           + Linguistic Abstraction: 
                -> Involves defining a new grammatical construct.
                -> Typically GOES BEYOND SYNTAX 
                   May INTRODUCE:
                        + NEW SEMANTICS 
                        + higher-level CONCEPTS.
            
                + Define: 
                    -> 2 phases: 
                        + 1. Define a NEW GRAMMATICAL CONSTRUCT 
                        + 2. Define the new construct's TRANSLATION into the kernel language
    
#### Language design: 
    ... 

#### Other translation approaches: 
    ... 

#### The Interpreter approach: 
    ... 





### 2.2 The single-assignment store 
    ... 

#### Declarative variables 
    ... 

#### Value store 
    ... 

#### Value creation 
    ... 

#### Variable identifiers 
    ... 

#### Value creation with identifiers 
    ... 

#### Partial values 
    ... 

#### Variable-variable binding
    ... 

#### Dataflow variables
    ... 





### 2.3 Kernel language 
