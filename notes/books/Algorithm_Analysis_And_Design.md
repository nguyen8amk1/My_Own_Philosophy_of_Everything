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

## Fundamental Data Structures: 
    -> Algorithms operates on data 
        -> WAYS TO ORGANIZE DATA(data structure) play a CRITICAL ROLE in the DESIGN and ANALYSIS of algorithms 
    Data structure:
        Scheme for organizing RELATED data items. 

    + Linear Data Structure: 
        + array 
        + linked list 
        + stack 
        + queue, priority queue

    + Graphs:  
        -> a collection of:
            + points/vertices/nodes
            + line segments/edges

        Graph: G = (V, E) trong do: 
            V: SET of vertices 
            E: SET of edges (edge: pair of 2 vertices) 
            vd: 
                V = {a, b, c, d, e, f } -> set of NODES 
                E = {(a, c), (a, d), (b, c), (b, f ), (c, e), (d, e), (e, f )} -> set of PAIR of nodes 

        2 types of Edge: 
            (u, v) mean: node u connected with node v (u -> v, directed)
            + Undirected: 
                pair of vertices (u, v) = (v, u) 
            + Directed: 
                pair of vertices (u, v) != (v, u) 
        3 states: 
            + complete: all vertices connect to all other verticies 
            + dense: only missing few edges compare to the complete 
            + sparse: miss a lot of edges compare to the complete
            -> depends on the state we CHOOSE DIFFERENT representation of the graph 

        2 representations: 
            + adjacency matrix: use for known ammount of nodes 
                -> better for dense graph
            + adjacency list: use for unknown ammount of nodes 
                -> better for sparse graph 

        2 properties: 
            + connectivity: 
                every node u have a path to node v  
                -> a graph with no connectivity will consist of many CONNECTED COMPONENT
                -> connected component: subgraph with no connection to other subgraph in the graph 
            + acyclicity: 
                graph with no cycle 
                -> cycle: path that start from u and end at u (khong trung edge)
            -> path: 
                simple: khong trung nodes  (vd: a, b, c, d, e)
                not simple : bi trung nodes (vd: a, b, a, c, e) -> trung node a 


    + Trees:   
        -> connected acyclic graph
        -> graph that acyclic but not connected = FOREST

        properties: 
            -> trees have some properties that normal graphs do not have: 
                + the number of edges is a tree is always one less than the number of vertices
                    |E| = |V| - 1
                + for every 2 vertices -> there always EXIST exactly 1 SIMPLE PATH from one to the other
                    -> we can SELECT ABTRARY VERTICES and call it a root -> Rooted tree
        keywords: 
            state-space trees: 
                very important tree that underlies 2 algorithms design techniques: 
                    + backtracking
                    + branch-and-bound

            ancestors: all the VERTICES on THE SIMPLE PATH from ROOT to vertex V 
                -> set of vertices

            decendents: all the VERTICES that the vertex V is the ANCESTOR (meaning V is on the simple path to those vertices)
                -> set of vertices 
                -> form a subtree rooted at V 

            depth: the LENGTH of the simple path from ROOT to V 
                -> TREE LEVEL = depth

            height: the the LONGEST of all the lengths of simple path from ROOT to a LEAF
                -> HEIGHT = MAX TREE LEVEL 

        3 types: 
            + Free tree: 
            + Rooted tree: 
            + Ordered Tree: 
                rooted tree with ALL THE CHILDREN of EACH VERTEX are ORDERED
                    -> ordered left to right 
                    -> BINARY TREE is an ORDERED TREE with 2 children left and right 
                    -> BINARY SEARCH TREE is an BINARY TREE with left child <= right child 
                        -> the EFFICIENCY of binary search tree DEPENDS on tree's HEIGHT 
                            logn <= h <= n - 1

        Representation: 
            + number of pointers = number of child 
            + first child-next sibling

    + Sets and Dictionaries:  
        Set: an UNORDERED COLLECTION (can be empty) of DISTINCT items called ELEMENTS
            can be DEFINED by:
                + EXPLICIT LISTING 
                    vd: {1, 2, 3, 4}
                + specify a PROPERTY that all elements must SATISFY 
                    vd: {n: n is a prime < 10}
                   
            Operations: 
                + checking membership: 
                    return true/false
                + union: 
                    return all the elements in 2 sets
                + intersection:
                    return all the COMMON ELEMENTS in 2 sets

            Implementation, 2 ways: 
                1. Bit vector/string 
                    -> all SETS are SUBSETS of a UNIVERSAL SET
                    -> if the UNIVERSAL SET have n elements 
                        vd: n = 6, U = {1, 2, 3, 4, 5, 6}
                        -> all the subset represented as a bit string/vector 
                            vd: subset S = {2, 4, 5}, bit vector = 010110
                    -> pros: 
                        fast operations
                    -> cons: large amount of storage 

                2. List structure
                    List vs Set: 
                        List: 
                            can contain identical elements
                            ordered -> change the order -> change the list 

                        Set: 
                            cannot contain identical elements
                            unordered -> change the order NOT change the set, it still the same set by nature

                    -> but we can still use list structure to implement Set, with some Set rules 


        Dictionary: 
            Operations: 
                + search for item 
                + add new item 
                + delete item 

        Set union problem: 
            ideas: 
                have n disjoint subset (each element is it own set, 1 element set)
                -> doing some combination UNION, SEARCH operations

            parition:
                of:  n-element set into 
                into: a collection of disjoint subset

            Operations: 
                + Union
                + Search


            keywords: 
                disjoint subsets: 
                    subsets that have no elements in common 

    + Abstract Data Types: 
        = a SET of DATA + a SET of OPERATIONS
        -> Basically all the Data Structure mention above

Things to know: 
    Combinatorial: 
        Product Principles: 