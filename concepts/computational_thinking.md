# COMPUTATIONAL THINKING 
learn from the course [Computational Thinking](../links/course_links.md)

Computational WORKFLOW: 
    data -> input -> process -> model -> visualize -> output: 
        data: 
        input: 
        process: modifying data 
        model: mechanism to understand the properties of the data 
        visualize: 
        output:  
Array:
    1d array: often called VECTOR
    2d array: often called MATRIX
    (n>2)d array: often called TENSOR

Abstraction: 
    -> know when the ABSTRACT things OUT and when the SPECIALIZED things IN 
    vd: an list of things with different types but have the same meaning (abstractly) but they're all different (concretely)
        -> know WHEN to UTILIZE the ABSTRACT MEANING of things and the CONCRETE MEANING of things is a must  
        vd: dynamic type language did another level of abstraction of static type language
            -> since it abstract the concrete type of the object 

Mutation: 
    there are 2 ways to compute something from an input 
        + modify that input - mutation (faster, but not safe)
        + create new result - non-mutation (safer, slower) -> try to keep doing this for the safety of the program 

    -> TIPS for writing non-mutating code: 
        writing non-mutating function is NOT TRYING TO REWRITE A MUTATING FUNCTION 
        -> it's CONSTRUCTING SOMETHING NEW 

Transformation: 
    Linear: 
    Non-linear: 

Automatic Differentiation: 
    symbollic differentiation: find the derivative using conventional way (vd: deriv x^2 = 2x)
    Automatic differentiation is DIFFERENT from that APPROACH 
        and it's different from (f - f')/something as well 

    Gradient: 
        -> DERIVATES of the functions IN EVERY ARGUMENTS(means more than 1) DIRECTION 
        -> input: vector of scalar values 
        -> output: vector of derivatives in every directions

    Transformations: 
        The relationship between Transformation and Vector(multidimensional) is the same as:
        Function and Number 