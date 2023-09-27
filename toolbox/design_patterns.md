# Design pattern

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

MVC: 
    + What TYPE of TOOL is this ?
        ....

    + What the REASON it created ? 
        .....
        -> the kind of problems they best suited 

    + How to USE it ? 
        .....

    + What makes it UNIQUE ? 
        .... 
        -> understanding the: 
            + capabilities 
            + constraints 
            -> help you pick the right tool for the job 

    MVC design pattern is easiest to understand when look at it's SEQUENCE DIAGRAM  
        -> Steps:
            1. The View takes the input (button, forms, ...) of the user 
            2. The View send the Event to the Controller 
            3. Controller process the Event input then send to the Model 
            4. The Model send back the Result to the Controller  
            5. Controller send the result back to the View  

    Model:
        Handle business logic, data manipulation/query and processing 

    Controller:
        Process the user event, input preprocessing into the format the Model can use 

    View:
        Data representation         
