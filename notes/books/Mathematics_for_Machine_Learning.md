# MATHEMATICS FOR MACHINE LEARNING
Machine learning is about: 
    designing algorithms that AUTOMATICALLY EXTRACT VALUABLE INFORMATION FROM DATA
    -> GENERAL-PURPOSE METHODOLOGIES that can be applied to many databases. (while producing something meaningful)

3 core concepts: 
    + data: 
        machine learning is data-driven 
            -> extract PATTERN from data, (ideally) without much domain-specific expertise.
    + model: 
        -> to extract PATTERN from data -> we need MODELs
        -> describe a process for GENERATING DATA
        -> a good model can then be used to predict what would happen in the real world without performing real-world experiments

    + learning: 
        (assume we are given a DATASET and suitable MODEl)
        -> a way to AUTOMATICALLY FIND PATTERNS and STRUCTURE in data
        -> by optimizing the parameters of the model

other concepts: 
    machine learning algorithm 2 meanings: 
        + predictor:
            -> system that MAKES PREDICTIONS based on INPUT DATA
        + training:
            -> system that ADAPTS some INTERNAL PARAMETERS of the PREDICTOR so that it performs well on future unseen input data

    + data as vectors: 
        -> think of data as vectors (assume data have been converted into numbers as vectors)
        -> there are 3 ways to think about vectors: 
            + array of numbers (COMPUTER SCIENCE view)
            + arrow with DIRECTION and MAGNITUDE (PHYSIC view)
            + a vector as an object that obeys ADDITION and SCALING (MATHEMATICAL view)

Two ways to read the books: 
    + Bottom-up: 
        + advantages: 
            -> can rely on previously learned concepts 
        + disadvantages: 
            -> foundational concepts might not interesting -> don't really remember the concepts when needed 

    + Top-down: 
        + advantages: 
            -> know WHY they need to work on a particular concept 

        + disadvantages: 
            -> knowledge build on shaky foundations

# Mathematics: 
    + linear algebra: 
        -> represent:
            + numerical DATA as VECTORs 
            + TABLE of such DATA as a MATRIX 

    + analytic geometry: 
        -> 2 vectors represent 2 objects in real world  
        -> need to make statement about the SIMILARITY between the 2 vectors/objects
        -> assume that SIMILAR INPUT vector give SIMILAR OUTPUT 
        -> analytic geometry: an OPERATION that DETERMINE the SIMILARITY between 2 vectors -> output a number that represents it 

    + matrix decomposition: 
        -> ....

    + probability theory: 
        -> to QUANTIFY THE CONFIDENCE we have about the VALUE OF THE PREDICTIONS (at a particular test of data)

    + vector calculus: 
        -> find parameters that maximize some performance measure 
        -> the concepts of GRADIENTS -> which tells us the DIRECTION in which to SEARCH FOR A SOLUTION.

    + optimization: 
        -> find the minima/maxima of functions 

# Machine learning: 
    + linear regression: 
        objective: 
            -> find FUNCTIONS that MAP inputs x of R^D to CORRESPONDING observed function values Y of R (interpret as label)
            -> INPUT X -> corresponding LABEL Y 

    + dimensional reduction: 
        -> find a compact, lower dimensional representation of x of R^D 
        -> only care about the MODELING the data -> NO LABELs associated with a data point x 

    + density estimation: 
        -> find a PROBABLITY DISTRIBUTION that DESCRIBES a GIVEN DATASET.
        -> NO LABELs -> interest in a density model that describe the data 

    + classification: 
        -> have LABELs (input x, label y) but the label is integer not real value 