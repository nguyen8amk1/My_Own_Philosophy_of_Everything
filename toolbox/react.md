React: 
    Stateful Logic: 
        any code that uses state 
        vd: a button contains a counter (state) 
        -> if we want to reuse the counter behaviour on any other components
            -> scatter/duplicated code 

    Reuse Stateful Logic: 
        render prop: share/reuse code between module 
            input: function 
            output: component (React element)
        higher order component: share/reuse component logic 
            input: component 
            output: component 

        -> pros: share state/behaviour between components 
        -> cons: require restructure of the involved components 
            -> create Wrapper hell (Higher Order Component wrapping, ...) 
            -> Hooks solve this problem 
        
    Hooks: 
        + What TYPE of TOOL is this ?
            Cross-cutting Concern separator

        + What the REASON it created ? 
            1. React doesn't offer a way to "attach" REUSABLE BEHAVIOUR to a component 
                -> HARD TO REUSE STATEFUL LOGIC 
                -> Hook EXTRACT STATEFUL LOGIC 
                    -> reused
                    -> tested independently 

            2. Complex components (contains related code but SPLITTED apart throughout the lifecycle methods): 
                vd: fetch data in componentDidMount
                    calls some random shit componentDidMount
                    process data in componentDidUpdate
                    -> RELATED CODE GET SPLITED APART 
                        WHILE UNRELATED CODE GET COMBINED TOGETHER 
                -> solution:
                    -> Use state management library (Redux)
                    -> Use Effect hook

            let you USE:
                + state 
                + other React features (what are they?? )
            WITHOUT WRITING A CLASS 

            -> the kind of problems they best suited:
                + Reuse stateful logic 
                + Split the related code into the same component 

        + How to USE it ? 
            ....

        + What makes it UNIQUE ? 
            from other means of reusing stateful logic like: render prop, HOC
                -> ....

            ....
            -> understanding the: 
                + capabilities 
                + constraints 
                -> help you pick the right tool for the job 

        