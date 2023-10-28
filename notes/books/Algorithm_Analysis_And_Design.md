# INTRODUCTION TO ALGORITHM ANALYSIS AND DESIGN 
note from: Introduction to The Design and Analysis of Algorithms, Anany Levitin 

## Fundamentals of Algorithm Design: 
## 1. Understand the problem 
    Problem UNDERSTANDING steps: 
        1. CAREFULY read the problem's description 
        2. Work through a few smalls examples MANUALLY. 
        3. Consider SPECIAL CASES. 

    Recognizing the PROBLEM TYPE: 
    Understading Existing Algorithms: 
        if there are known algorithms for a problem, it's beneficial to understand:
            + how they work
            + strengths
            + weaknesses
            -> give you information to CHOOSE among different algorithms

    The Importance of SPECIFYING INPUTS: 
        -> PRECISELY SPECIFY the SET OF INSTANCES the algorithm need to handle.
        -> If do this INCORRECTLY could lead to the algorithm NOT WORKING FOR ALL THE CASES (edge cases)

## 2. Choosing between EXACT and APPROXIMATE Problem Solving 
    Exact Algorithm: find the PRECISE SOLUTION to a problem.
    Approximate Algorithms:  approximate solution is acceptable 
        use when Exact solution is NOT FEASIBLE or TOO SLOW 
        -> Approximation algorithms can BE PART OF more complex algorithms that aim to SOLVE a problem EXACTLY.

## 3. Algorithms Design Techniques: 
    -> GENERAL APPROACHES (strategies/paradigms) to solving problems algorithmically.
    -> There are many design techniques: 
        -> distill key ideas proven to be useful in algorithm design.
    -> NOT every general technique will be APPLICABLE TO ALL PROBLEMS, together they form a POWERFUL TOOLBOX for algorithm designers.
## 4. Algorithm and Data Structure: 
    -> COMBINING MULTIPLE TECHNIQUES and designing algorithms that don't neatly fit existing design techniques can be necessary.
    -> It's crucial to CHOOSE APPROPRIATE DATA STRUCTURES for the operations performed by the algorithm
    -> The choice of data structure can significantly impact algorithm efficiency.
## 5. Proving Algorithm's Correctness: 
   -> Mathematical INDUCTION is a common technique for proving the correctness of algorithms 
        -> algorithm iterations naturally provide a sequence of steps suitable for such proofs. 

## Important Problem Types: 
## Sorting: 
    -> rearranging items in a list in non-decreasing order
    -> assuming a total ordering RELATION EXISTS AMONG THE ITEMS. 
    -> Items can be:
        + numbers
        + characters
        + strings
        + records with keys. 
            (key: piece of information as a key to guide the sorting process)

    -> Can be use as an AUXILIARY STEP in other algorithms

    2 properties: 
        + stable: preserves the relative order of equal elements in the input (deo hieu :v)
        + in-place: not using extra memory 

## Searching:
    -> FINDING a SPECIFIC VALUE, known as a search key, within a GIVEN SET
    Considerations for Searching Algorithms:
        + Different algorithms vary in terms of speed and memory requirements.
        + Some algorithms are HIGHLY EFFICIENT but may only work with SORTED DATA.

## String Processing:
    String matching problem: Searching for a specific word within a text

## Graph Problems:
    Realworld applications:
        + transportation
        + communication
        + social and economic networks
        + project scheduling
        + games.

    Basic Graph Algorithms: 
        + Graph-TRAVERSAL algorithms: 
            -> Finding paths through a network.
        + SHORTEST-path algorithms: 
            -> Determining the best route between two points.
        + TOPOLOGICAL SORTING for graphs with directed edges: 
            -> Checking the consistency of courses and their prerequisites

## Combinatorial Problems: 
    -> abstract problems that involve FINDING A COMBINATORIAL OBJECT
        vd:
            + permutation
            + combination
            + subset
            -> that SATISFIES specific CONSTRAINTS 
        -> may also require the COMBINATORIAL OBJECT to HAVE additional PROPERTIES, vd: maximum value or minimum cost 

    -> Most of these problems LACK known algorithms that can SOLVE THEM EXACTLY in an ACCEPTABLE AMOUNT OF TIME.
        -> no efficient exact algorithms for them

    -> There are still SOME EXCEPTION that can be SOLVED EXACTLY, vd: shortest-path problem

## Geometric Problems:
    -> solving problems related to GEOMETRIC OBJECTS such as points, lines, and polygons

    Two Classic Problems: 
        The closest-pair problem: 
            -> Given n points in the plane, find the pair of points that are closest to each other.
        The convex-hull problem: 
            -> Find the smallest convex polygon that encloses all the points in a given set.

## Numerical Problems: 
    -> involve MATHEMATICAL OBJECTS of CONTINUOUS NATURE
        vd: 
            + solving equations
            + computing definite integrals
            + evaluating functions
    -> These problems typically require approximate solutions.
    ....