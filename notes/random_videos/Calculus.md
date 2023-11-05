# Essence of Calculus 
notes from: https://www.youtube.com/watch?v=WUvTyaaNkzM&list=PLZHQObOWTQDMsr9K-rj53DwVRMYO3t5Yr&ab_channel=3Blue1Brown

Intergral: Area under the curve 
    -> use to solve hard problem which involves: 
        sum of many small values 
            (vd: quang duong xe chay tang toc roi dung lai, the speed is not constant -> can't use a normal formula)
            -> reframe as an area under a graph 
    -> basically a function getting the area under a graph:
        input: graph (equation)
        output: area (number)

    notes: 
        let's call: A(x) is the integral of f(x) 
        dx: is a small nudge (chieu rong)
        f(x): is the function that you need to calculate the integral (chieu dai)

        dA = f(x)*dx (chieu dai*chieu rong): 
            (dA: the small change in A, dx: small change in x)
            -> the rectangle that use for calculate the integral (by sum all the rectangles up) 

        dA/dx = f(x) (the RATIO of: small change in A/small change in x)
            -> We don't know what inside A(x)
            -> this is PROPERTY A(x) must have 
            -> This RATIO is the "DERIVATIVE" of A(x)

        dA = (A(x + dx) - A(x))
            -> dA/dx = f(x)

        -> Derivative of A(x) = dA/dx = (A(x+dx) - A(x))/dx
        -> Derivative of f(x) = df/dx = (f(x+dx) - f(x))/dx
            -> the rate of change around a point x  
        @@ Computing derivatives via differntiation ?? 

Derivative: 