# RANDOM TERMINOLOGIES

## Scaling: 
    make node(s) process more inputs 
    2 types:
        Vertical Scaling:
            making a single Node stronger  -> process more inputs 
            either through: 
                + code optimization
                + add more hardware to the node 

        Horizontal Scaling 
            adding more nodes -> process more inputs 

    -> Each have its own pros and cons 

## Specification (Dac ta): 
    ....

## Hook: 
    + What TYPE of TOOL is this ?
        Behaviour modifier
        -> 3 Types (In the context of programming): 
            + Event hooks: 
            + Life Cycle hooks:
            + API Hooks: 

    + What the REASON it created ? 
        a means of executing custom code (vd: function) before/after/replace the existing code 
            vd: "hook" the Captcha function before the login processing function 
        -> the kind of problems they best suited: 
            CUSTOMIZE/EXTENDS the BEHAVIOUR of an existing system or application 
            without MODIFYING its core code.
            -> ADD/ALTER FUNCTIONALITIES at a SPECIFIC POINTS 

        -> Let's ABSTRACT THE MEANING out a little bit:
            -> original process composition: 
                A -> B -> C
            -> a hook D will try to insert itself into the composition, before C:
                A -> B -> D -> C

            -> The hook is the MORPHISM (the MEANS of EXECUTION), not the OBJECT

    + How to USE it ? 
        ....

    + What makes it UNIQUE ? 
        ....

        -> understanding the: 
            + capabilities 
            + constraints 
            -> help you pick the right tool for the job 

## Higher-Order-Components:
    Definition: 
        Is a Components that does at least 1 of the following: 
            + takes functions as arguments
            + return function as its results 

    + What TYPE of TOOL is this ?
        Manipulator/Modifiers: it's MANIPULATE/MODIFY other Components 

    + What the REASON it created ? 
        ....
        -> the kind of problems they best suited 

    + How to USE it ? 
        ....

    + What makes it UNIQUE ? 
        Abstaction of Behaviour: 
            As you implementing the (Higher Order) function
            you only need to worry about the "What" you want the function to achieve
            then inject the "How" it achieve from the outside
            -> Allow "HOT RELOAD"/DYNAMICALLY CHANGE THE BEHAVIOUR without writing entirely repeated new code

        Modularity and Composition: 
            ....

        Functional Transformation: 
            ....

        Closure creation: 
            ....

        -> understanding the: 
            + capabilities 
            + constraints 
            -> help you pick the right tool for the job 

Conclusion: 
    -> Both Higher Order Function and Hooks are kinda related but Hooks are even more abstracted (higher level of abstraction)
        -> Higher Order Function which is more concrete (lower level of abstraction)
            -> can be use to implement Hooks

## Middleware: 
    a service that could be used in multiple situations 
    provide abilities that you don't have to build everything from scratch everytime working on a new project
    to reuse the handling of complex repsonsibility that you don't want to develop from scratch 
    vd: 
        handle bilions of simutanious database queries ? -> don't want to develop your own solution
            -> use middleware

    in Express: 
        middleware is any code sit between The Request and Response
        have ability to: 
            run logic
            modify request, response object  (passing info to the next middleware)
            calling next middleware in the chain

## Normalize: 
    the process that makes something more 'normal'
        the "normal" meaning might change in different context:
        vd: 
            Data Normalization: reduce data to canonical form (chinh tac)
            Database normalization: reduce to normal form to reduce data redundancy, increase integrity 
            ....

## Intergration: Find the AREA under the curve ()
    -> using small rectangles 

## Differentiation: Find the GRADIENT of the curve (Opposite process to intergration)
    -> using small triangles

## Synchronous: 
    ... 

## Asynchronous: 
    ...

## Định tính: 
    Qualitative 
    thông tin và dữ liệu dưới dạng ‘phi số’ để có được các thông tin chi tiết về đối tượng nghiên cứu

## Định lượng:
    Quantitative
    thông tin và dữ liệu dưới dạng số học, số liệu có tính chất thống kê để có được những thông tin cơ bản, tổng quát về đối tượng nghiên cứu

## Context (programming-term): 
    ... 

## Methodology (phuong phap luan): 
    ... 
## Epistemology (khoa hoc luan): 
    ...

## Methodology vs Epistemology: 
    ... 

## Reasoning: 
    ...


## Evaluate: 
    FINDING the numerical value or RESULT of a mathematical EXPRESSION or EQUATION.
