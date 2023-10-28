# MATHEMATICS FOR MACHINE LEARNING
Machine learning is about: 
    designing algorithms that AUTOMATICALLY EXTRACT VALUABLE INFORMATION FROM DATA
    -> GENERAL-PURPOSE METHODOLOGIES that can be applied to many databases. (while producing something meaningful)

3 core concepts: 
    + data: 
        machine learning is data-driven 
            -> extract PATTERN from data, (ideally) without much domain-specific expertise.
    + model: 
        -> to extract PATTERN from data -> we need MODELs
        -> describe a process for GENERATING DATA
        -> a good model can then be used to predict what would happen in the real world without performing real-world experiments

    + learning: 
        (assume we are given a DATASET and suitable MODEl)
        -> a way to AUTOMATICALLY FIND PATTERNS and STRUCTURE in data
        -> by optimizing the parameters of the model

other concepts: 
    machine learning algorithm 2 meanings: 
        + predictor:
            -> system that MAKES PREDICTIONS based on INPUT DATA
        + training:
            -> system that ADAPTS some INTERNAL PARAMETERS of the PREDICTOR so that it performs well on future unseen input data

    + data as vectors: 
        -> think of data as vectors (assume data have been converted into numbers as vectors)
        -> there are 3 ways to think about vectors: 
            + array of numbers (COMPUTER SCIENCE view)
            + arrow with DIRECTION and MAGNITUDE (PHYSIC view)
            + a vector as an object that obeys ADDITION and SCALING (MATHEMATICAL view)

Two ways to read the books: 
    + Bottom-up: 
        + advantages: 
            -> can rely on previously learned concepts 
        + disadvantages: 
            -> foundational concepts might not interesting -> don't really remember the concepts when needed 

    + Top-down: 
        + advantages: 
            -> know WHY they need to work on a particular concept 

        + disadvantages: 
            -> knowledge build on shaky foundations

# Mathematics: 
    + linear algebra: 
        -> represent:
            + numerical DATA as VECTORs 
            + TABLE of such DATA as a MATRIX 

    + analytic geometry: 
        -> 2 vectors represent 2 objects in real world  
        -> need to make statement about the SIMILARITY between the 2 vectors/objects
        -> assume that SIMILAR INPUT vector give SIMILAR OUTPUT 
        -> analytic geometry: an OPERATION that DETERMINE the SIMILARITY between 2 vectors -> output a number that represents it 

    + matrix decomposition: 
        -> ....

    + probability theory: 
        -> to QUANTIFY THE CONFIDENCE we have about the VALUE OF THE PREDICTIONS (at a particular test of data)

    + vector calculus: 
        -> find parameters that maximize some performance measure 
        -> the concepts of GRADIENTS -> which tells us the DIRECTION in which to SEARCH FOR A SOLUTION.

    + optimization: 
        -> find the minima/maxima of functions 

# Machine learning: 
    + linear regression: 
        objective: 
            -> find FUNCTIONS that MAP inputs x of R^D to CORRESPONDING observed function values Y of R (interpret as label)
            -> INPUT X -> corresponding LABEL Y 

    + dimensional reduction: 
        -> find a compact, lower dimensional representation of x of R^D 
        -> only care about the MODELING the data -> NO LABELs associated with a data point x 

    + density estimation: 
        -> find a PROBABLITY DISTRIBUTION that DESCRIBES a GIVEN DATASET.
        -> NO LABELs -> interest in a density model that describe the data 

    + classification: 
        -> have LABELs (input x, label y) but the label is integer not real value 

# Linear algebra: 
    An algebra is a concept includes:
        + a set of objects (object)
        + a set of rules to manipulate these objects (morphism)

    -> Linear algebra: 
        + object: vector
        have some rules to manipulate vectors

    Vector: 
        special object that can be:
            + added together
            + multiply by scalars 
            -> produce another object of the same kind
        -> ANY OBJECT THAT SATISFIES THESE 2 PROPERTIES  -> can be considered a vector 
            vd: 
                + Geometric vectors: 
                    + added together: 
                        -> two vector can be added which output another vector 
                    + multiply by scalars: 
                        -> a vector can be multiply by scalar to have a longer vector in the same direction

                + Polynomials: 
                    + added together: 
                        -> 2 poly can be added which results another poly
                    + multiply by scalars: 
                        -> poly can also mult by a scalar results another poly  

                -> Notes: geometry vectors is very DIFFERENT from Polynomials: 
                    -> geometry vector is actual CONCRETE drawing
                    -> polynomials is ABSTRACT concepts 

                + Audio signal: is also a vector 
                    + added together: 
                    + multiply by scalars: 

                + Elements of R^n (tuples of n real numbers): 
                    is more abstract than polynomial 

    Important idea in Mathematics is "CLOSURE": 
        -> What is the SET OF ALL THINGS that can RESULT FROM my proposed OPERATIONS ? 
            -> Starting with a small set of things 
            -> Doing some operations with things in that sets
            -> Does those RESULTS still IN THE SAME SET ? 
                -> if it does -> you HAVE CLOSURE UNDER THOSE OPERATIONS
        Notes: 
            closure is a PROPERTY/CHARACTERISTIC of SET not an object 
            closure describe: 
                HOW a particular SET OF OBJECTS BEHAVES UNDER SPECIFIC MATH OPERATIONS. 
                indicating whether the RESULTS of CERTAIN OPERATIONS performed on the elements of the set STAY WITHIN THE SAME SET

        -> When apply to vector we have: 
            What is the SET OF VECTORS that can RESULT BY starting with a SMALL SET OF VECTORS
                and ADDING them to each other and SCALING them ? 
                -> This result a VECTOR SPACE 

## System of Linear Equations
    Many PROBLEMS can be FORMULATED as SYSTEMS OF LINEAR EQUATIONS: 
        -> Linear algebra give us TOOLS to solve them.
    In general: 
        for a real-valued system of linear equations, we obtain either: 
            + no 
            + exactly one
            + infinitely many 
            -> solutions

    SYSTEMATIC APPROACH to solving systems of linear equations:  
        -> use a useful compact notation
        -> COLLECT the COEFFICIENTS aij into VECTORS 
        -> COLLECT VECTORS into MATRICES
    
    Geometric Interpretaion of System of Linear Equations: 
        every EQUATION represent by a line, plane, ...  
        the SOLUTION represent by a point, line, plane, empty, ...

    Matrix can be used to COMPACTLY REPRESENT: 
        + Systems of linear equations
        + Linear functions (linear mapping)

# Matrix: 
    Not all matrix have inverse 
    If inverse exist -> then that matrix is called regular/invertible/nonsingular matrix, and that inverse is unique 
    else -> called singular/nonintertible 

    DETERMINANT of a matrix can be used to CHECK whether a MATRIX IS INVERTIBLE 

    Compact Representation of System of Linear Equations as: Ax = B

    GENERAL SOLUTION for solving system of linear equations: 
        3 steps: 
            + Find a particular solution to Ax = b   
            + Find all solutions to Ax = 0
            + Combine the solutions from steps 1, and 2 to the general solution 

        -> can only solve system in SIMPLE FORM 
        -> most system are not in this SIMPLE FORM -> need to transform them to SIMPLE FORM 
        -> Gaussian Elimination

    Elementary Transformation: 
        -> KEY to solving a system of linear equations 
        -> TRANSFORM the equation system into a SIMPLER FORM
        -> but still KEEP the SOLUTION set the SAMR
        have 3 transforms: 
            + EXCHANGE of TWO EQUATIONS (rows)
            + MULTIPLICATION of an EQUATION (rows) with a CONSTANT 
            + ADDITION of TWO EQUATIONS (rows)

        SIMPLE FORM: 
            [1, 2, 3, 4]*[x1, x2, x3, x4]T

## VECTOR SPACE 
    Group definition: 
        basically: 
            a SET of elements G
            and an INNER OPERATION X that defined on these elements 
            that keep 4 structure of the set intact: 
                1. CLOSURE of G under operation X
                2. ASSOCIATIVITY: 
                3. Neutral Element:  
                4. Inverse Element: 
                If it also have commutative -> it's a Abelian Group
    -> Set of R^nxn with operation . is a group (not Abelian) called "General Linear Group"
        Consists of invertable matrices 

    Inner operators: only operates on the elements in set G
    Outer operators: operates on an element in set G and an element in other set

    Vector space: 
        is a set V = (V, +, .) with 2 operators 
            + inner operator (vector addition): + : V x V -> V 
            + outer operator (multiplication by scalar): . : R x V -> V
        Elements in V are called VECTORS.

        Notes: 
            multiplication by scalar != scalar product 

        properties: 
            1. (V, +) is an Abelian group
            2. Distributivity
            3. Associativity (outer operation)
            4. Neutral element with respect to the outer operation
            
    Vector subspace: 
        sets contained in the original vector space  
        with the property:
            when we PERFORM VECTOR SPACE OPERATIONS on elements WITHIN THIS SUBSPACE
            -> we will never leave this subspace -> we're TRAPPED 

        Vector subspace (or Linear subspace) are KEY IDEA in machine learning 

        V = (V, +, .) a vector space
        U con cua V, U khac rong 
        U = (U, +, .) => U is a vector subspace of V 

        with 2 additional properties: 
            + U is NOT EMPTY, in particular 0 belong to U 
            + CLOSURE of U: 
                With respect to: 
                    + outer operation: 
                    + inner operation: 

        -> Every "SUBSPACE U" con cua (R^n, +, .) is the "SOLUTION SPACE"
            of a homogeneous system of linear equations Ax = 0 for x belong to R^n ?? 

## Linear Independence 
    Basis: 
        a SET of vectors 
        which we can REPRESENT EVERY VECTOR in the vector space 
        by ADDING them together and SCALING them.

    Linear combination: 
        the sum of whole bunch of vector each have it's own coefficient/lambda constant
        -> linear combination with all coefficient/lambda constant is 0  -> TRIVIAL LINEAR COMBINATIONS
            -> LINEAR INDEPENDENT 
        -> linear combination NOT all coefficient/lambda constant is 0  -> NON-TRIVIAL LINEAR COMBINATIONS
            -> LINEAR DEPENDENT with at least 1 coeffecient = 0

Things to know: 
    First order logic: []
    Set builder notation: [X]

    Homogeneous system of linear equations: 
        ...
    Inhomogeneous system of linear equations: 
        ...