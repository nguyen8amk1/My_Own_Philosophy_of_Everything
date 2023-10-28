# Data Structures
Find answers to these questions: 
    + What TYPE of TOOL is this ?
    + What the REASON it created ? 
        -> the kind of problems they best suited 
    + How to USE it ? 
    + What makes it UNIQUE ? 
        -> understanding the: 
            + capabilities 
            + constraints 
            -> help you pick the right tool for the job 

# Linear data structures: 
    store data ONE AFTER THE OTHER (sequentially)
    + Array: 
        can store just a simple value 
        but can also store more complex data structure -> Node (1 VALUE, 1 LINK)
        -> can BUILD ALL OTHER DATA STRUCTURES on top of Node (vd: linked list)

    + Queue: can also be implemented using linked list (or Nodes)
    + Stack: can also be implemented using linked list 

# Non-linear data structures:
    element are not stored sequentially (vd: Trees and Graphs)
    also build using _node (with 1 VALUE and N LINKS)

    + Trees 
        PUT CERTAIN RULES, OPERATIONS on top of a bunch of _nodes 
            rules: 
                + no link duplicates node 
                + no link to the head
                ....
                -> we have a tree, added more/less rules -> have different types of trees (vd: balance tree, binary search tree,...)

    + Graphs
        REMOVE ALL THE RULES OF A TREE -> we have a graph 
        Added more or less rules -> have different types of graphs (vd: directed graph, ...) 