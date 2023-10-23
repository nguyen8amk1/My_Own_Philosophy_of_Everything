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

Related works are called: PHYSICAL REALIZATION OF 3D MODELS
    -> The current MOST RELATED WORK is called: 
        Legolizer: A Real-Time System for Modeling and Rendering LEGO Representations of Boundary Models
            -> convert 3d model into LEGO build without actually analyse whether it can be physically built or not :v 

## Layout optimization: 
    Other's work focus on finding the interlocking layout without consider the force-balance 
        -> since the interlocking layout is independent from the size of the build 
        -> it does not fully reflect stable of the build according to it's size

    -> use simple friction model 

    Layout design problem: has a discrete nature 
        -> locations, orientations, sizes of LEGO bricks   
        are allowed to TAKE only DISCRETE VALUES 
        -> Motivating DEDICATED METHOD for layout GENERATION

## Overview: 
    Problem definition: 
        input: 3d model with colors 
        VOXELIZE the 3d model: use Chen and Fang's algorithm (Fast Voxelization of Three-Dimensional Synthetic Objects)
        Hollow the object (to reduce the number of bricks)
            Keeps all voxels in 3 voxel-width
        Consider brick family: 
            1 × 1, 1 × 2, 1 × 3, 1 × 4, 1 × 6, 1 × 8, 
            2 × 2, 2 × 3, 2 × 4, 2 × 6, 2 × 8
            *bricks with OTHER SIZES can be EASILY INCORPORATED 

        tries to find: VOXEL-FILLING-LAYOUT (the layout where the bricks exactly fill the non-empty voxels -> match 100% with the desire output)
            satisfied: 
                + MAXIMAL (toi gian, no bricks can be merge into larger brick)
                + physical realizable 

        Core idea: 
            Start with an arrangement that's not perfect
            Make small adjustments that are local and random 
                -> get a new layout that are better in someways compare to the previous one. 
                -> do this over and over again 
            Because there is a limited number of arrangement -> eventually we will find it 

            2 Stage: 
                1. initialization 
                2. stability-aware refinement -> update the layout to improve stability 
                    -> focus only on the important section of the structure 

        Structural Analysis technique:        
            return 2 important things:
                + structure metric:     
                    -> HOW WELL the structure is ORGANIZED or build 
                    -> need 2 capabilities (for a good metric): 
                        + HELP DECIDE the ORDER in which different structure are better or worse
                        + Set threshold for when to stop making changes.

                + structure critical portion: 
                    -> the SPECIFIC PART of the structure that NEEDS IMPROVEMENT 

            In the init step: 
                SIL (the metric of the init) = number of connected component  
                WIL (the critical portion of init)  = regions with different connected component in their neighborhood

            In the stability-aware refinement step:
                use force-based analysis -> return SRL, WRL 


Questions: 
    What's a discrete nature ? 
        ....
    What's a CONNECTED COMPONENT ? 
        a set of bricks such that:
            between any 2 bricks in the set, there exist a path of bricks
            where consecutive bricks are snapped together

        -> single connected components  = bricks in the layout as a whole is a connected component