# FRAMEWORK FOR 
    # + HOW TO LEARN NEW CONCEPTS FROM A CONCRETE EXAMPLE -> Procedure Abstraction (get the general procedure to solve a type of problem)
    # + HOW TO APPLY CONCEPTS -> Pattern matching (how to find the right tool for the right job)

Procedure Abstraction (Removing Hooks): 
    Scenario: Procedure of solving a math problem
        -> we have step a, b, c, d, e, f, ...
        and then the problem solved 
        but when we face another problem of the same type 
        the original procedure (the concrete procedure that you have just learned before that) don't really apply directly
        -> So why it's that ?? 
        It's because the original procedural have too many HOOKS
        [Hooks](../RANDOM_TERMINOLOGIES.md):
            -> It's distract you from the main business logic   

    -> YOU MIGHT NEED TO SOLVE A LOT OF CONCRETE PROBLEM 
        AND WRITE THE DETAILS STEP OUT OF AND GET THE COMMON BETWEEN THEM 

    Things to identify from a concrete procedure: 
        Hooks: the additional operation that you need to do along the way (that goes between different main logic step)
        Business logics: the main step(goals) to solve the problem 
        -> The UPPERCASE letter is the main step
        -> The lower case letter is the hooks 

        vd: A-> a -> b -> B -> e -> f -> C 
            -> this is a concrete procedural that normally used to solve a problem 
            -> How to ABSTRACT the concrete procedural into a general one that can be used:
                -> REMOVE ALL THE HOOKS 
                -> A -> B -> C

        The Hooks are also general procedural 
        that can be LEARNED SEPARATELY
        to INSERT between steps of a DEFINED PROBLEM SOLVING PROCEDURE(Business Logic)

Pattern matching: one of the most powerful method to problem solving 
    it's closely ties to Category Theory 
    -> it's main method is to FOCUS ON THE RELATIONSHIP between Objects rather than the object itself
    -> means the OBJECTS DETAILS are just DISTRACTING you from seeing the ABSTRACT PATTERN 
    -> Abstract Pattern is the pattern that forms from the relationship of objects (STRINGS CONNECT TO EACH OTHER)
    -> Focus on the ABSTRACTED RELATIONSHIP PATTERN is way easier to identify which PATTERN is which 

    -> This method can apply to any field -> since problem solving patterns are abstract concepts 
            -> but need to have a pattern galery first 
   
    vd: 
        Choosing design pattern for a particular context: 
            -> have a design pattern galery (in string pattern/diagram form)
            -> analyse the the relationship between objects 
            -> form a concrete pattern from the context
            -> match with the design pattern(in string pattern/diagram form) -> can choose the right one 



-> STORE THE PATTERN/RELATIONSHIP OF OBJECTS IN YOUR HEAD 
    -> OUTSOURCE(STORE THEM ELSEWHERE, vd: papers, other people head :v) THE OBJECTS DETAILS 
    -> Pattern/Relationship of Objects is actually the thing you need to solve problems (or come up with solutions)