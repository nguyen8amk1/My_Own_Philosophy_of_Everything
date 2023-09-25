MY FRAMEWORKS: 
    THINGS YOU NEED TO KNOW BEFORE CHOOSING AMONG TOOLS (DEDUCE FROM 7DB7W): 
        Learn to make choice given:
            + particular needs  
            + resource at hand 
                understand your options: 
                    -> good, bad options 
                    -> Gets your hand dirty to figure out these questions -> understand the options
                        + What TYPE of TOOL is this ?
                        + What the REASON it created ? 
                            -> the kind of problems they best suited 
                        + How to USE it ? 
                        + What makes it UNIQUE ? 
                            -> understanding the: 
                                + capabilities 
                                + constraints 
                                -> help you pick the right tool for the job 

        The questions to ask is: 
            Should i use this to ... ?
            not Can i ....
            -> the questions is LESS about the solutions is COMPLETE FIT with your problem
                but rather it's the BEST FIT given your:
                    + problem space
                    + usage pattern 
                    + available resources 

        Instead of pure dominance of any particular strategy: 
            -> we'll see increasingly SPECIALIZED SOLUTION
            -> each suited for a particular (can be overlapped) SET OF IDEAL PROBLEM SPACE 

        -> @TEST: USE THIS FRAMEWORK TO UNDERSTAND THE NATURE DATA STRUCTURES AND ALGORITHMS 

    GOOD ENOUGH PHILOSOPHY: 
        One of the best(hardest) skills you can ever learn: 
            KNOW WHEN TO STOP: 
                There is a threshold for digging into a rabbit hole 
                But the finding value of the threshold is the problem 
                    -> You can't really found the sweet spot without getting your hands dirty  
                    -> Need a lot of try and error to get it right 
                Digging a knowledge too deep could actually hurt your learning process rather than improving it   
                -> GOOD ENOUGH IS THE STATE THAT YOU DON'T ACTUALLY KNOW ALL THE INS AND OUTS OF THE KNOWLEDGE BUT YOU CAN STILL BENEFIT FROM IT, YOU CAN TRY TO DIG DEEPER AT OTHER TIME  
                -> The threshold best value is the "good enough" 

        Things won't be perfect given the time and technology we currently having 
        Use the thing that is a cut-down version rather than waiting for a perfect to come 
        -> Try to apply the current knowledge 
            (even though it's not perfect match for everything or even well thought out -> know when the stop researching and actually use the knowledge) 
            then refines it afterwards (involve the users in the trade-offs) 

        Questions: WHAT ARE THE PROPERTIES TO CONSIDER ? 

    SYSTEM DESIGN: 
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


    HOW TO LEAD A TEAM: 
        Goal: all members have the same big picture in mind 
        Tools: 
            Diagram:
                Use case diagram
                Class diagram 
                Sequence diagram 
            Rules: 
                vd: rules for file structure,... 

    LEARN HOW TO DECIDE (HOW TO BE DECISIVE): 
        This is right up the hardest thing i've ever wanted to learn  
        and still can't do it right 
        Really want to know how to be a decisive person ?? 
            -> What i TRULY WANT are:
                + Learn to admit the problem with my decision 
                + Learn to actually decide the thing that good on the whole, not just me 
                    (i tend to delay the decision so that i could wait for the timing that beneficial on my part only) -> The reason why i become indecisive -> Selfish TT
                -> These thing should become INSTINCE 
        .....

    HOW TO AQUIRE A NEW SKILLS: 
        First step in aquirring a new skill: 
            is being able to reproduce what others have done before you. 
        not doing your own thing. 
        -> Reproducing things the quickest way to mastering a skill 

    HOW TO LEARN A NEW PROGRAMMING LANGUAGE (Deduce from 7L7W): 
        Knowing multiple paradigm greatly improve your design skill 

        Getting started with a language is try to:
            + keep the syntax correct
            + understand the syntax error 
            + get a working program 
            -> The brain will ACTIVELY learning this 
        -> NOT try to understand the core principles that the language embodied 
            -> the brain will LEARN THIS IN THE BACKGROUND rather than you try to learn it from the start
            -> one day you wake up and you will magically understand it 
        NOTE: 
            Programming is about understanding of ideas
            More exposure to new ideas -> deepen the understanding of what programming is all about 

            The first language give you tools to get through everyday tasks.
            The second language help you encounter the new world. 
                -> knowing new languages SHAPE THE WAY YOU THINK 

        The process: 
            Goal: experience the language in a controlled enviroment (IDE,...)
                -> some way to GET A WORKING PROGRAM AS FAST AS POSSIBLE without much fuss 
                looking for:
                    + a snap shot of syntatic sugar
                    + core concepts 

            Find answer to these questions: 
                + What is the TYPING MODEL?: 
                    + strong (Java)
                    + weak (C)
                    + static (Java)
                    + dynamic (Ruby)
                    -> Typing model affects: 
                        + the TRADE-OFF that developer have to deal with 
                        + the WAY TO ATTACK THE PROBLEM 
                        + control the WAY THE LANGUAGE WORKS 
                + What is the PROGRAMMING MODEL?: 
                    + OOP  
                    + FP 
                    + Procedural 
                    + Hybrid 

                    -> Learning PROGRAMMING PARADIGMS is one of the MOST IMPORTANT concepts 

                + How will you INTERACT with it?: 
                    -> How to get it running ? 
                    -> What environment does it run in ? 
                    + compiled 
                    + interpreted
                    + does it have VM or not ? 

                + What are the:
                    + decisions constructs
                        + if
                        + while 
                        + other constructs that way differents than what you have ever seen 
                    + core data structure: 
                        + collections, containers 

                + What are the CORE FEATURES that make the language UNIQUE ? 
                    vd: some support: 
                        + advance feature for CONCURRENT PROGRAMMING
                        + unique high-level constructs: 
                            + closure macros
                            + message interpretation 
                            +...


    LEARN HOW TO SWITCH BETWEEN ABSTRACT AND CONCRETE MINDSET: 
        Abstract thinking: 
            helps you to see the similarity between phenomenons  

        Concrete thinking: 
            helps you to see the differences between phenomenons  
            
        -> You need both thinking to be a good problem solver 

        My problem is that:     
            i saw the world too abstractly sometimes -> i can't remember the details, just vauge objects instead ? 
        .....

    A MASTER PLAN TO SOLVE PROBLEMS (which should counter my weaknesses in problem solving):
        My weaknesses: 
        My strengths: 

        Strategy: 
            Divide the problem: 
                Divide the problem into discrete sub problems (steps)
                ....
                
            Reduce the problem: 
                Remove some contraints in oreder to make the (divided) problem easier to solve 
                ....
        ....
