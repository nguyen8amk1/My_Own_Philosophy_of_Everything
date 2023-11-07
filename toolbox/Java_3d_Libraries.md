# JAVA 3D LIBRARIES 
## JME3: 
SimpleApplication class: 
    + MANAGES 3d scene graph 
    + checks for user INPUT 
    + UPDATES the game state 
    + automatically DRAWS the scene to the screen 

Understanding the terminologies: 
    I want to create a CUBE -  i CREATE:
        a GEOMETRY 
        with a 1x1x1 BOX SHAPE 
    I want to use a blue color - i CREATE: 
        a MATERIAL with 
        a blue COLOR PROPERTY 
    I want to COLORIZE the CUBE blue. - i SET: 
        the MATERIAL 
        to the BOX GEOMETRY 
    I want to ADD the cube to the scene - i ATTACH: 
        the BOX GEOMETRY 
        to the ROOTNODE 
    I want the cube to appear in the center - i CREATE: 
        the BOX at the 
        ORIGIN = Vector3f.ZERO 

Introduction to Scene Graph: 
    Scene graph: the virtual space that your game happens in
    Spatials: Objects in scene graph 
        have 3 properties:
            + location/translation
                -> defined using x, y, z coordinates
                Y is upward
                X is right 
                Z is toward you 

            + rotation
            + scale 
        2 types of spatials: 
            + Geometry: VISIBLE spatials
                have 2 properties: 
                    + mesh: define its FORM 
                    + material: define its APPEARANCE      

                -> Use case: Store objects looks 

            + Nodes: 
                -> are spatials that can have other spatials as children 

                chilren of node A are:
                    + moved  
                    + rotate 
                    RELATIVE to their parent node (node A)

                ALL NODES in the scene graph CONNECTED to the BASE ROOT NODE  

                -> Use case: GROUPING  

    Culling: 
        means: 
            + that a geometry is NOT RENDERED by the gpu 
            + the geometry is still processed as part of the scene graph 
                but all RENDERING-related OPERATIONS are SUSPENDED 
        3 states: 
            + always 
            + never 
            + inherit (default)

        Automatic culling: 
            -> Cull geometries that are NOT IN THE VIEW of the camera 

    -> Every concepts in here have methods to call to set that property in the Spatial objects 
