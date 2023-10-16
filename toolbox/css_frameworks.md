# CSS FRAMEWORKS 
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

Bootstrap: 
    + What TYPE of TOOL is this ?
        css library 
    + What the REASON it created ? 
        ....        
        -> the kind of problems they best suited 
    + How to USE it ? 
        Installation:
            CDN:
            npm:
                can be install through npm so that node-base front end framework can use it 
            Bower
            Composer

            -> Bootstrap also has javascript file for:
                + Components: vd: drop down, navbar
                + Animation: 

                (2 files, jquery, and bootstrap.js, since it's build upon jquery)
        Normal styling: 
            ....

        Responsive: 
            ...
    + What makes it UNIQUE ? 
        Predesigned look and feel -> most bootstrap app, look just like bootstrap  
        Responsive implementation: Grid system 

        -> understanding the: 
            + capabilities 
            + constraints 
            -> help you pick the right tool for the job 

Tailwind:
    + What TYPE of TOOL is this ?
        ....
    + What the REASON it created ? 
        ....
        -> the kind of problems they best suited 

    + How to USE it ? 
        Installation:
            + Tailwind CLI:
            + Using PostCSS:
            + Framework specific installation: framework's command that support tailwindCSS
            + CDN: 
                play CDN is designed for development purpose only -> not good for production
            -> allow:
                + config
                + custom css
                + enable first-party plugin (tailwind own plugin) -> not install, just enable them

        Core concepts:
            + Utility-First: declarative, composition styling instead of imperative styling  
                -> building COMPLEX COMPONENTS FROM A CONSTRAINED SET OF PRIMITIVES utilities
                -> inline styling

                pros:
                    + don't have to INVENTING CLASS NAME, NO NAMING -> no BEM, no nonsense
                    + rarely need to write custome CSS -> SMALL CSS FILE
                    + CSS file is global, while inline css is local -> MAKING CHANGES FEELS SAFER

                cons:
                    it's looks long, ugly
                
                Utilities vs traditional inline styling:
                    + have CONSTRAINTS in term of DESIGN -> NO MAGIC NUMBER like when using inline-style
                        -> have predefined design system

                    + responsive design: have PREDEFINED RESPONSIVE UTILITIES instead of writing @media queries 
                        -> normal inline don't have that

                    + Hover, focus, and other states are handled using STATE VARIANTS
                        -> normal inline don't have that 

                    + Maintainability: change repeated styling (since Tailwind approach will have a a lot of repeated styling string)
                        solution:
                            Loops
                            Extracting:
                                + Components:
                                + Partials:


    + What makes it UNIQUE ? 
        Doesn't have pre-designed components -> create your own style through composing utilities
        Responsive implementation: Flex-box

        -> understanding the: 
            + capabilities 
            + constraints 
            -> help you pick the right tool for the job 

    -> TODO: write the same TODO-APP in both lib