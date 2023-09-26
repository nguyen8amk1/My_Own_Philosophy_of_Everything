# SYSTEM DESIGN: 

*High level Design: 
    -> Come up with technologies to solve problems
    Steps: 
        1. Define requirements from the users perspective 
            -> pick out the most important user's requirements -> technical requirements
        2. Reduce the features to data definition 
            -> Make abstract/concepts into concrete properties  
        3. Defines endpoints(vd: API) where data can be: 
            + manipulate 
            + queried 
            -> Each for every features 

    -> Goal: create a system that easily:
        + scale 
        + extend  in features 
        when requirements change 

    API Design: 
        Different API have different behaviours: 
            + continous
            + prediorically 
            + rarely called  
            +...
            -> Require different PROTOCOL for each behaviour
        -> Try to match the API behaviour with suitable protocol 
        -> Choose correctly could greatly IMPROVE THE PERFORMANCE 

    Choose Database: 
        -> Choose base on pros, cons that benefit the storing requirements 

*Low level Design:
    -> The clearer the API spec the easier the LLD will be 

    Use composition of 3 diagram: 
        Use case Diagram -> Class Diagram -> Sequential Diagram 

    Use case Diagram: User-System Interaction Diagram 
        -> What the user expect from the system (happy path)

    Class Diagram: 
        specify the:
            + states
            + behaviours 
        of objects in the systems
        -> Can create multiple Objects to handle the requirements 

    Sequence Diagram: (I think is the most useful)
        How the user interact with different modules of the system as time pass (relative to time)
