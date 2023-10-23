# DIAGRAMS
Use Case Diagram: 
    ....

## Sequence Diagram: 
    Show the INTERACTION between objects   
    in SEQUENTIAL ORDER (that those interactions occur)
    -> documenting how a system should behave 
    -> USE CASES are often REFINED into one or more SEQUENCE DIAGRAM  
    -> FOCUS on the ORDER in which the messages OCCUR, not the message themselves 

    Basics: 
        Axes: 
            Horizontal: message sending  
            Vertical: time 

        *Components: 
        Lifelines: 
            -> drawn as a box with dashed line decending from center of the bottom edge 
            -> represent the ROLE of the instances PARTICIPATE in the SEQUENCE being modeled 

            name: 
                underline = specific instance
                not underline = general role 

        Messages: 
            to show an object (life line) sending a message to another object 
            draw a solid line with: 
                + SOLID arrow head -> synchronous call 
                + STICK arrow head -> asynchronous call 
            name on top of the arrow 
            MESSAGE that being called is implemented as the METHOD OF THE RECEIVE OBJECT  

            return value draw as: (optional) 
                dashed line with stick arrow head 

        Guard: 
            CONDITION that MUST BE MET in order for a message to be sent to the object
            format: [boolean_value test] message_call()