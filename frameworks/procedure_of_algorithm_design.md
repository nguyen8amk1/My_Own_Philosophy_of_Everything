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

