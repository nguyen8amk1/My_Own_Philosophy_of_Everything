# Procedural of algorithm design 
notes from class

keywords: 
    + Define Problem: 
    + Formulation: 
        https://www.youtube.com/watch?v=KxI_2h95Gq4
        https://www.youtube.com/watch?v=ABMPgSApdUw
        https://www.youtube.com/watch?v=WZIyL6pcItY

        *** Introduction to Integer Linear Programming: https://www.youtube.com/watch?v=kkx3PaHLoek

        *** Integer Programming Introduction: https://www.youtube.com/watch?v=eiDsoNmYlx8
            -> This does have formulation and stuff, so probably watch this first 


    + Objective function:   
        https://www.youtube.com/playlist?list=PLMHSr8fseBzUHy1RaUmnpGH0bPFmUk7VS

    Discrete optimization:?? == integer optimization ??  
        https://www.youtube.com/watch?v=-YoPG0xI9-8 
        https://www.youtube.com/watch?v=hhg9gQp_SKM

Linear programming vs (Mix) Integer Programming: ?? 
    Differences:  
        LP: variables are real numbers -> continous
        IP: variables are integers -> discrete 

They are:
    + Decision-making framework:
    + Proof of optimality 
        -> they have built in functionality to PROOF the OPTIMISM of decision
    + Common language for mathematical modeling: 

NOTE: 
    EQUATIONs = CONSTRAINTs

They(LP, IP) can: 
    solve system with MORE EQUATIONS/CONTRAINTS than UNKNOWNS 
        -> which matrix can't do 
    -> MORE EQUATIONS THAN UNKNOWNS MEANS there are unlimited solutions to the problem  
    -> But matrix can't find the optimal one from those 
    -> BUT LP and IP CAN -> FIND THE OPTIMAL SOLUTION IN THE VAST SET OF SOLUTIONS 


## ALGORITHMs: 
### Backtracking: 
    key thing to identify: 
        + S = <S1, S2,...,Sn> - what is it 
        + The choices of each Si (each Si have their own set of choices or all same)
            vd: 
                S1 could have 3 choices (2, 3, 4)
                S2 could have 5 choices (2, 3, 4, 4, 4)
                S3 could have 2 choices (2, 3)

        + Validation constraints: 
            ... 
            -> This is probably the hardest parts (i still can't defined it correctly)

    -> **Identify these wrong everything is wrong


### Greedy: 
    key thing to remember: 
        ...

### (Greedy) Best-First-Search (BFS): 
    Prerequisites: 
        + Uninformed Search: 
            -> Have no information about the search space 
            vd: Breath-First-Search, Depth First Search 
        + Heuristic, Informed Search: 
            -> Know some information about the search space ?? (what are the some information ??)
                vd: 
                    HOW FAR we are from the goal? 
                    HOW TO reach the goal?

             vd: Best-First-Search

    Breath-First-Search idea:
        have an OPEN queue to save the states 

    COST FUNCTION: 
        f(n) = g(n) + h(n)
        NOTE: 
            we have 3 nodes: 
                + s: start node
                + n: current node
                + e: end node 

            g(n): the accumulative length from s to n  
                (the CONCRETE VALUE that you actually adding every time you move to the next node)  

            f(n): the estimate length from n to e 
                (the value that you got given from the problem statement or in real life is some information that you one given to you pre-hand)

        Basically f(n) is like this: 
            f(n) = s -> n -> e = concrete(s, n) + fuzzy(n, e)



    Best-First-Search: 
        -> Pick the "best" node as next node to expand 
            according to some RULES-OF-THUMB -> called Heuristic

        -> Heuristic: an APPROXIMATE MEASURE of HOW CLOSE you are to the TARGET ? 
                f(n) = h(n)
                where h(n) = estimated cost from node n to the goal. 

### Divide and Conquer:  
    Steps: 
        + 1. DIVIDE into small SUBPROBLEMS.

        + 2. CONQUER subproblem RECURSIVELY. 

        + 3. COMBINE SOLUTIONS of SUBPROBLEMS into 1 original problem 
    
    Template: 
        void DC(N) { // N: Kich thuoc du lieu  
            if (N small enough) {
                Solve the subproblem        
            } else {
                <Divide the original N problem into small sub problems N1, N2, ..., Nm>

                for(i = 1, i < m, i++) {
                    DC(Ni);
                }

                <Combine the results>
            }
        } 

    Have 2 types: 
        + Divide kho, Combine de: 
            -> vd: QuickSort
        + Divide de, Combine kho 
            -> vd: MergeSort 

    NOTE: 
        Divide and Conquer can ONLY be SOLVED using TOP DOWN approach 
    
### Decrease and Conquer:  
    DECREASE the INPUT SIZE rather than DIVIDE into sub-problems 
    3 types of decreases: 
        + giam theo HANG SO (constant)
        + giam theo HE SO (factor)
            vd: n/2, n/4, n/8, ...
            vd: binary search 
        + giam GIA TRI THAM SO (variable size decrease)
            vd: UCLN 

    Flow: 
        P(n) -> P'(m) -> Solve P'(m) -> Deduce -> Solve P(n)
        NOTE: m < n

    vd: Tinh giai thua: n!
        -> giam theo HANG SO, HANG SO = 1 
   
    NOTE:
        Decrease and conquer can be SOLVED using; 
            + top-down: (recursion)
            + bottom-up: (for loop)

        Best workflow: 
            TOP-DOWN ANALYSIS to UNDERSTAND THE PROBLEM
            then SOLVE using BOTTOM-UP

        **THE MOST IMPORTANT THING TO FIGURE OUT 
            -> INSERT TECHNIQUES
            -> each problem have their own rule of insertion  
    
    TEMPLATE: 
    vd: 
    // S: list of current results: {{1}, {2}, {3}, {4}, {1, 2}, ...}  
    // a: list of number to insert vd: {1, 2, 3, 4}

    hoanvi(a, n) {
        S = {a0}
        for(i = 1 -> n-1)
            P = empty 
            foreach x in S
                P = P + insert(x, a[i])
        S = P
    }

### Dynamic Programming: 
    An UPGRADE of Divide and Conquer
    -> If you CAN SOLVE with Divide and Conquer 
        -> can solve with Dynamic Programming 

    It's a like Divide and Conquer in a sense like: 
        Top-down analysis  
        then solve Bottom-up  
        but if there are too many REPLICATED CALCULATIONS 
        -> then use Dynamic Programming to CACHE the results 

    + Use some Data Structure the cach the results: 
        either: 
            + 1D array 
            + 2D array 
            ...

    + Dynamic Programming Equation:  
            Equation of: 
                + WHERE to take the PREVIOUS RESULTS for CALCULATION 
                + WHERE to SAVE the new results 

        **NOTE: 
            + if you find out the CT Truy hoi -> DP Equation
            + must find out DP Equation before continuing to the next step 

            but CT Truy hoi != DP Equation 

            
        vd: to hop chap k cua n 
            CT Truy hoi: C(k, n) = C(k, n - 1) + C(k -1, n -1)
            -> DP Equation: C[i][j] = C[i-1][j-1] + C[i -1][j]

    + Basic Steps: 
        + Figure out what DATA STRUCTURE to use. 
        + FILL in some of the CELLS corresponse to the BASE CASE. 
        + Establish DP Equation. 
        + FILL in ALL CELLS. 
        + Extract FINAL RESULTS.

    New: 3 Basic steps: 
        + 1. PHAN TICH DAC TRUNG cua loi giai toi uu: 
            + 1. Optimal Substructure 
                -> Loi giai toi uu cua cha = tong hop loi giai toi uu cua con 
                    *kinda like Greedy*
                -> Find out the RELATIONSHIP between the PARENT and CHILD. 
            + 2. Overlapping

        + 2. TAO BANG: lap day bang theo 1 quy luat nao do 
            + gan gia tri cho mot so o nao do (base case).
            + xac dinh gia tri cua cac o khac nho vao gia tri cac o truoc do. 

        + 3. TRA BANG: 
            -> truy xuat loi giai bai toan

    NOTE: able to solve the problem top down first 
        -> find the relationship of the parent and child 

    + Bai toan toi uu: 
        **Phan tich dac trung: 
            + 1. Optimal Substructure 
                -> Loi giai toi uu cua cha = tong hop loi giai toi uu cua con 
                    *kinda like Greedy*
                -> Find out the RELATIONSHIP between the PARENT and CHILD. 

            + 2. Overlapping

        vd: tim chuoi con chung dai nhat 
            Xn: a b d a c f
            Yn: b d a c f a d d 

        ...


     some more hints: https://courses.csail.mit.edu/6.006/spring11/exams/notes3-dp       

##### Main steps of solving a dynamic programming:
    1. Define the subproblems
    2. Find HOW TO COMBINE SOLUTIONS to SUBPROBLEMS to form solutions to larger subproblems
    3. Choose an ORDER TO SOLVE SUBPROBLEMS so the problems they depend on are solved before combining solution


    **These 3 steps have to be satisfied when giving a dynamic programming solution.  


#### Combining solutions: 
    there a FEW MAJOR WAYS to COMBINE SOLUTIONS:     
        + Prefix/Suffix:  
            Start with solving smaller subproblems 
                from beginning and expand subproblems toward the end 
                or 
                from end and expand subproblems toward the begnning  

            Useful: when the problem has a NATURAL ORDER or STRUCTURE that CAN BE EXPLOITED.

            
            + Visualize:
                vd: the ASSEMBLY LINE as a sequence of tasks:
                    Task 1 -> Task 2 -> Task 3 -> ... -> Task n

                Solve subproblems starting from Task 1 and expand towards Task n, 
                OPTIMIZING EACH TASK IN SEQUENCE.

            NOTE: 
                -> have a predetermined starting point, (first element or last element)
                -> have a direction to expand 

        + Substring:  
            Solving smaller subproblems substrings and expand outwards
            Useful: USE this in problems where we CAN’T TAKE ADVANTAGE OF PREFIX/SUFFIX structures (which means have NO ORDER)
            
            Note: 
                "expand outwards" meaning: 
                    emphasizes the iterative and step-by-step nature of the process
                    systematically extend solutions from smaller to larger substrings
                    highlights the progression in the expansion of the considered substrings

                -> More general and versatile than prefix/suffix 
                    -> can solve prefix/suffix problem while the reverse cannot 

                -> have a no predetermined starting point
                -> not have any direction 
            

            Multiplication Parentheses:
            vd: Visualize a sequence of numbers:
                a1 * a2 * a3 * ... * an
                -> Solve subproblems for smaller substrings, 
                    such as (a1 * a2) * (a3 * a4), 
                    and expand outward until the entire sequence is considered.
            


        + Combination (not understand):  
            Combining solutions involves:
                using a multi-dimensional table to store solutions, 
                with EACH DIMENSION USING A DIFFERENT COMBINATION STRUCTURE 

            This is common when solving problems where ORDER MATTERS and the SOLUTION RELIES ON MULTIPLE FACTORS.

            NOTE: 
                + Combination structure: 
                    ... 

                + How does 2d table works: 
                    the key to understand is to recognize that 
                        + each DIMENSION represent different PARAMETER in the problem 
                        + the TABLE is used to efficiently STORE and RETRIEVE SOLUTIONS to subproblems.

                    Typically: 
                        one dimension of the table: represents the SIZE or INDEX of the SUBPROBLEM, 
                        other dimension: represents a DIFFERENT PARAMETER or aspect of the PROBLEM.

                        In the context of Knapsack problem: 
                            + Rows (First Dimension):
                                Rows REPRESENT DIFFERENT ITEMS OR CHOICES AVAILABLE in the problem.
                                Each row (indexed by i) corresponds to a different item or a decision point in the problem.
                                    -> different items = different parameters

                            + Columns (Second Dimension):
                                Columns represent different VALUES or states of a parameter in the problem.
                                Each column (indexed by w) corresponds to a different state of the REMAINING CAPACITY of the knapsack.
                                    -> Remaining capacity = Number = SIZE 
                                    -> Parameter "w" (weight)

                            -> The entry dp[i][w] represents: the OPTIMAL SOLUTION for the SUBPROBLEM with the FIRST I ITEMS and REMAINING CAPACITY W.

                + The order of combining solutions from different cells in the table may involve a combination of prefix, suffix, or substring structures.
                    vd: the order of combination of in the Knapsack problem in the columns (horizontal direction) is prefix structure

                    You can understand this as: 
                        + prefix/suffix: is typically called as the "first i items" approach, that works on 1d array 
                            -> since each row, column of a dp 2d table is a 1d array, you may use this technique on those rows, columns. 


        + Tree:  
            The tree approach involves:
                solving smaller subproblems at the leaves 
                expanding upwards level by level until the root subproblem is solved.

            useful: for problems with a HIERARCHICAL or RECURSIVE STRUCTURE.

#### Adding constraints: 
    A common mistake: 
        -> define the subproblem WITHOUT ENOUGH CONSTRAINTS. 

    If you’re having trouble working out a dynamic programming solution, 
        LOOK FOR OTHER PARAMETERS THAT YOU MIGHT BE ABLE TO FIT INTO THE SUBPROBLEM TO CONSTRAIN IT FURTHER.

    EXTRA CONSTRAINTS may MAKE COMBINING SUBPROBLEMS MORE STRAIGHTFORWARD and be the KEY TO SOLVING A DYNAMIC PROGRAMMING PROBLEM.

    It may add more runtime, but sometimes we have to add constraints to the subproblems and a slower
    correct solution will often get more points than an incorrect solution anyway.

    vd: 
        WIdget layout (added WIDTH CONSTRAINT),
        Knapsack problem (added SIZE CONSTRAINT)

#### Running time: 
    Calculating the runtime of a dynamic programming solution involves computing: 
        + how many subproblems there are 
        + how long it takes to solve each subproblem.

        The runtime is usually (Time per subproblem) × (Number of subproblems).
