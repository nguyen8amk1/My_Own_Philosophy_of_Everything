# Legolization: Optimizing LEGO Designs
Building LEGO sculpture requires accounting for the target object's: 
    + shape
    + color
    + stability 
    -> finding a good LAYOUT of LEGO bricks that prevents sculpture collapsing  

Using force-based analysis 
    -> output: 
        + the weak portion of the sculpture
        + estimate the stability of the given sculpture 
    the analysis uses friction and normal forces as parameters (collected through physical experiments) 
    -> know whether the build of the sculpture was possible or not 
    -> LAYOUT REFINEMENT ALGORITHM -> iteratively IMPROVES THE STRUCTURE AROUND THE WEAK PORTION 

Refinement technique to update the LEGO layout (to improve the weak portions)
    -> randomly finding initial layout where all bricks are connected 
        -> form a SINGLE CONNECTED COMPONENT
    -> iterative perform: 
        + stability analysis
        + local reconfiguration


Previous research use heuristic-based(theo kinh nghiem) -> not very accurate, optimized