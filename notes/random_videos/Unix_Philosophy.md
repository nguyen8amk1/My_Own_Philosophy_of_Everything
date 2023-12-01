# UNIX PHILOSOPHY 
notes from video: https://www.youtube.com/watch?v=-RqoPoOQd7w

## Original: 
    Write PROGRAM that DO ONE THING and DO IT WELL 
    Write programs to HANDLE TEXT STREAMS, because that is a UNIVERSAL INTERFACE 

## Favourite version: 
    1. Small is beautiful 
        -> Creation of SMALL, FOCUSED programs that do one thing well 
        -> Emphasizes: 
            + Simplicity  
            + Clarity 
            -> EASIER to UNDERSTAND, MAINTAIN, TROUBLESHOOT

        "SMALL THINGS have TREMENDOUS ADVANTAGES over their larger counterparts.
        Among these is the ability to combine with other small things in unique and useful ways."

        -> Ability to COMBINE with OTHER SMALL THINGS in UNIQUE and USEFUL WAYS

    2. Make each program do one one thing well.
        -> A program should have a specific and well-defined purpose.

        ELIMINATE: 
            + overhead 
            + unnecessary complexity 

    3. Build a prototype as soon as possible. 
        "Most USERS looking for a new piece of software WON'T KNOW WHAT THEY REALLY WANT UNTIL THEY SEE IT, 
        so REQUIREMENTS DOCUMENTS are often MISLEADING about the USERS' REAL NEEDS."
        -> GIVE THE USER SOMETHING, anything, UP-FRONT TO CRITICISE, and WORK FROM THERE.

        -> Quickly developing a basic version a the program to:
            + TEST 
            + VALIDATE 
            core functionality. 
            -> Helps identify: 
                + DESIGN FLAWS 
                + Usability issues
                + potential improvements  

    4. Choose portability over efficiency. 
        -> PRIORITIZES creating software that RUNS ON DIFFERENT PLATFORMS
        -> make sure the program will run on that hardware with MINIMAL EFFORT.

        QUOTE: "If today's hardware just about runs a program with just about adequate efficiency, tomorrow's will run it with power to spare."


    5. Store data in flat text files. 
        -> Storing data in textfiles instead of complex binary formats 

        -> Data is only useful AS LONG AS IT'S BEING USED, 
        and FLAT FILES help ENSURE that DATA IS USABLE FOR THE LONGEST POSSIBLE TIME.

    6. Use software leverage to your advantage. 
        -> Encourages:
            REUSING EXISTING SOFTWARE COMPONENTS and libraries 
            rather than reinventing the wheel.

        -> Leverages the collective effort -> Efficiency in development 

    7. Use shell scripts to increase leverage and portability.  
        -> enable CHAINING SIMPLE PROGRAM to CREATE more COMPLEX WORKFLOWS. 

    8. Avoid captive(tù) user interfaces.
        Captive user interface: 
            -> is the interface that REQUIRES the users to MANUALLY EXIT
            before dropping back to a prompt.  

            vd: ncurces interface is such captive one 
                https://upload.wikimedia.org/wikipedia/commons/2/27/Linux-menuconfig.png

        Non-Captive user interface: 
            -> is the tool that does what is suppose to do and 
            take you back to the prompt. 

        QUOTE: A program which prevents user from using any other commands for the duration "captures" the user 
        and prevents him from taking advantage of other commands

    9. Make every program as a filter 
        -> Design programs that: 
            + PROCESS INPUT 
            + PRODUCE OUTPUT
            -> acting as FILTER in DATA TRANSFORMATION PIPELINE.
        -> MODULARITY and COMPOSABILITY of software components. 

        NOTE: ONLY MODIFY DATA, NEVER CREATE IT.
