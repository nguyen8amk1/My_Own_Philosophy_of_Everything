# THE PRAGMATIC PROGRAMMING 

Orthogonality/Independence: 
    -> Othogonality often it's an IMPLICIT feature of other methods and techniques 
    -> LEARN IT DIRECTLY IS WAY BETTER 
    -> Orthogonality means vuong goc 
        -> move along one of the line, your position projected on another line doesn't change 

    ## Non Orthogonal system: is like a helicoper  
        -> 1 parameter change cause everything else to change 
        -> super complex to use 
        -> COMPONENTS ARE HIGHLY INTERDEPENDENT 

    ## Orthogonal: 
        -> WE WANT TO DESIGN COMPONENTS THAT ARE:
            + self contained 
            + interdependent
            + single, well-defined purpose 
            -> can change without having to worry about the rest of the system 
                -> AS LONG AS THE INTERFACE OF THE COMPONENT DOESN'T CHANGE 
            
        2 benefits of Orthogonality: 
            Productivity: 
                Changes are LOCALIZED -> easier to develop, test,...
                Promote REUSE: 
                    if components have specific, well-defined responsibilities
                    -> can be combined with other components, in a way that have never accounted for 
                    -> the more LOOSY COUPLED the system, the EASIER TO CONFIGURE and REENGINEER

                vd: Component A does M distinct things 
                    Component B does N distinct things 
                    A and B are orthogonal 
                    -> THERE ARE MxN NEW THINGS IT CAN DO IF YOU COMBINE THEM 

            Reduce risk: 
                + less fragile 
                + diseased sections of code are isolated -> can be destroy or fixed independently without affect others
                + easily tested 
                + not as tightly tied to a particular:
                    + vendor
                    + platform
                    + product 
                    -> cause the INTERFACES TO THESE THIRD-PARTY COMPONENTS will be ISOLATED TO SMALLER PARTS of the overall development  
    
    ## Ways to apply the principles of orthogonality: 
        ### Project Teams: 
            If a team is not orthogonal 
                -> every changes needs a meeting of an entire team 
                -> cause every changes affect everything 

            -> HOW TO ORGANIZE TEAMS TO GROUPS WITH WELL-DEFINED RESPONSIBILITIES AND MINIMAL OVERLAP ?? 
                + it depends on:
                    + project 
                    + ANALYSIS of the areas with POTENTIAL CHANGES 
                    + PEOPLE you are AVAILABLE 

                -> Separating MAJOR INFRASTRUCTURE components (vd: database, GUI, middleware layer, ...)
                    -> each MAJOR get its own SUBTEAM 
                    -> divide people into each accordingly

                -> (Informal) MEASUREMENT of HOW ORTHOGONAL of the Project Teams
                    Each change involved HOW MANY PEOPLE ? 
                        -> the LARGER the number -> the SMALLER orthogonal
        ### Design: 
            Layered approach is a powerful way to design orthogonal system 
                -> Each layer:
                    + provide a LEVEL OF ABSTRACTION 
                    + uses only the ABSTRACTION provided by the LAYERS BELOW it 

            -> Orthogonal design test: 
                Ask question: 
                    + if change the REQUIREMENTS behind a particular function 
                        -> how many modules are affected ? -> the answer should be '1' (there might cause changes is other FUNCTIONS as well, but it should always within single MODULE)
                    + How decoupled your design from changes in the real-world ?
                        vd: Are you using telephone number as customer id ? 
                        -> DON'T RELY ON PROPERTIES OF THINGS YOU CAN'T CONTROL 

        ### Toolkits and Libraries:     
            Be careful to preserve the orthogonality of your system 
            as you INTRODUCE third-party TOOLKITS and LIBRARIES 


    DRY goal: 
        -> minimize duplication within a system 
    Orthogonality goal: 
        -> reduce the interdependency among the system's components 

    IF YOU CHANGE 1 THING AND 4 OTHER THINGS GO WRONG -> IT'S TIME TO REFACTOR 

    ## Challenges: 
        Consider: 
            Windows's large GUI tools 
            Linux small command line tools but combinable 
            -> Which is easier to use for exactly the purpose for which is was intended ? 
                -> Windows GUI tools is easier for the purpose it was intended 
                -> Because the GUI is easie to use and it only designed to do one thing 

            -> Which set is more orthogonal and WHY ? 
                -> small command line tools are more orthogonal 
                -> Because: 
                    + ....

        C++ supports MULTIPLE INHERITANCE 
        Java allows a class to implement MULTIPLE INTERFACES 
        -> What impact does USING THESE FACILITIES have on othorgonality ?  
            + ....

        -> Is there a DIFFERENCE IN IMPACT between using multiple inheritance and multiple interfaces 
            + ....

        -> Is there a DIFFERENCE between using DELEGATION and INHERITANCE 
            + ....