# Legolization: Optimizing LEGO Designs
notes from research: 
    http://www.cs.columbia.edu/~yonghao/siga15/luo-Legolization.pdf
    https://dl.acm.org/doi/10.1145/2816795.2818091
 

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
## Layout Reconfiguration 
    Given: 
        + current layout L 
        + structure critical region WL  
    -> Do: 
        1. Identify: RECONFIGURATION REGION Nk(WL) 
            -> the UNION of:
                + WL 
                + WL's K-ring NEIGHBORS
                (vd: k=1 -> 1-ring neightbor is the direct neighbor)
        2. Modify: 
            LOCALLY MODIFY the layout for Nk(WL)
                -> Using ALGORITHM 2 

        If k (in k-ring) is large enough to include the entire sculpture 
            -> RECONFIGURE the layout FROM SCRATCH  

        ->  if there exists a satisfactory maximal layout, 
            we can eventually find that layout 

        -> Basically: if locally reconfig not found any good layout -> do it from scratch 

        Keep k small, only increase it when there is no better layout 
            k = f/N + 1
            trong: 
                f: fail count 
                N: 10 (magic number :v) 

        Generate reconfigured layout use: (like previous method vanZijl and Smal 2008)
            3 OPERATIONS: 
                + split
                + repeated
                + remerge
            with:
                varying RECONFIGURATION SIZE 
                extended COLOR ASSIGNMENT RULE 
                
        Algorithm 2: Layout Reconfiguration 
            Input: 
                + layout L
                + critical portion WL
                + fail count f

            Output: -> reconfigured layout L'
                steps: 
                    1. compute k from f using k = f/N + 1
                    2. Nk(WL) <- k ring neighbour from WL 
                    3. Sk <- SPLIT bricks in Nk(WL)
                    4. L' <- randomly and repeatedly remerge bricks in Sk
        Explained: 
            Brick SPLIT: 
                1. Identify the bricks Nk(WL) 
                    within the K-RING 
                    of the CRITICAL PORTION WL

                2. SPLIT bricks in Nk(WL): 
                    into a SET OF 1X1 BRICKS.
                    with their color RESET to the INPUT VOXEL COLOR.

            Random REPEATED and REMERGE: 
                Input:
                    the set of 1x1 bricks  
                Do: 
                    Iteratively and randomly MERGE 2 neighbouring bricks that are MERGEABLE
                    until no more bricks can be merged -> use less bricks  
                    Mergable if: 
                        + the merged brick still belong to the standard LEGO brick family 
                        + the merge does not violate the Color Assignment Rule 

            Color Assignment Rules: 
                bm: the merged brick from input (2 bricks bi, bj)
                cm: the color of the merged bricks bm with input (2 bricks bi,bj color ci, cj)

                cm is decided through following rules: 
                    1. Both ci and cj are IGNORED: cm is assigned IGNORE  
                    2. one of ci or cj is IGNORED and the other with specific color  
                       -> cm is the specific color 
                    3. ci, cj are the same color -> cm = ci 
                    4. ci, cj different color: 
                        if hard color constraints -> NOT MERGE bi, bj
                        else 
                            use IMPORTANCE SAMPLING STRATEGY (Probabiliistic method)
                            to assign either ci, or cj to cm
                            such that it LESS likely to VIOLATE THE COLOR ALIGNMENT.

                IGNORED means: not visible 
                        
## Resources: 
A Fast VOXEL TRAVERSAL ALGORITHM for Ray Tracing: 
    -> http://www.cse.yorku.ca/~amana/research/grid.pdf

## Questions: 
    What's a discrete nature ? 
        ....
        -> ultilize searching algorithm 

    What's a CONNECTED COMPONENT ? 
        a set of bricks such that:
            between any 2 bricks in the set, there exist a path of bricks
            where consecutive bricks are snapped together

        -> single connected components  = bricks in the layout as a whole is a connected component
