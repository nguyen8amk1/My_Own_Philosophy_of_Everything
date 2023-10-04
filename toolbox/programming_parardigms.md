# PROGRAMMING PARADIGMS

Object Oriented: 
    + What TYPE of TOOL is this ?
    + What the REASON it created ? 
        -> the kind of problems they best suited 
    + How to USE it ? 
    + What makes it UNIQUE ? 
        -> understanding the: 
            + capabilities 
            + constraints 
            -> help you pick the right tool for the job 

Functional: 
    + What TYPE of TOOL is this ?
    + What the REASON it created ? 
        -> the kind of problems they best suited 
    + How to USE it ? 
    + What makes it UNIQUE ? 
        -> understanding the: 
            + capabilities 
            + constraints 
            -> help you pick the right tool for the job 

Aspect Oriented: @Current 
    Primitives: 
        + Aspect: 
            ....
        + Concerns: Logic/Functionality 
            + Core concerns:  
                -> Primary functionality of the system 
                vd: Business logic 

            + Cross-cutting(system-wide) concerns: 
                -> Logic/Functionality that AFFECT several modules (vd: logging, authentication)
                -> without the possility to encapsulated in any single module 
                -> result of:
                    + scattering (code duplication)
                    + tangling (dependencies between systems)
                vd: logging, security, data transfer 
                    -> needed in almost every module of an application

        -> Core concerns (business logic): Vertical line goes straight from top to bottom
        -> Cross-cutting (system-wide) concerns: Horizontal line that CROSS THROUGH ALL the Vertical (core concerns)
    -> Try to separate these cross-cutting concerns 

    + What TYPE of TOOL is this ?
        Programing paradigms

    + What the REASON it created ? 
        Aim to increase modularity 
        by allowing the separation of cross-cutting concerns. 

        -> the kind of problems they best suited: 
            Separate code that affects multiple modules 
            (meaning if it's change many module affected -> need to separate it into it's own block so that when it's change nothing affected )

    + How to USE it ? 
        ....

    + What makes it UNIQUE ? 
        ....
        -> understanding the: 
            + capabilities 
            + constraints 
            -> help you pick the right tool for the job 