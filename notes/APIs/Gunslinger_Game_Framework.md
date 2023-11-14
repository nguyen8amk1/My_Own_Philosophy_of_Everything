# GUNSLINGER GAME FRAMEWORK
notes from this video: https://www.youtube.com/watch?v=-_HxKDNuCqA&t=900s
along with its source code: https://github.com/MrFrenik/gunslinger/
    with all the documentation in gs.h 

## "Engine" Context
    Single, global engine context which HOLDS ALL LAYER DATA 
        gs_engine_t *engine = gs_engine_instance();
    GLOBALLY ACCESSIBLE 

## Math 
    Standard 3d containers (vector, matrice, quaternion)
        + gs_vec 
        + gs_mat
        + gs_quat

    math operations (translation, rotation, scale)
        + gs_vqs 
        -> does supply parent/child hierachy transformation

## Container 
    hash table: gs_dyn_array(T)
    dynamic array: gs_hash_array(K, V)
    slot array 
    slot map 
    byte buffer 

## Framework Layers 
    All FRAMEWORK LAYERS can be REDEFINED and OVERRIDEN 
        -> Must write code for IMPLEMENTATIONS for all API FUNCTIONS of the layer
    All DATA for LAYERS contained in SIMPLE STRUCTS 

    MECHANISM for GETTING DATA provided from the framework: 
        gs_platform_t *platform = gs_engine_subsystem(platform);

## Layer List:  
## + Platform Layer
    Abstract OS specific operations and utilities: 
        + Window creation
        + Graphics API context registration and creation  
        + File loading/reading/writing
        + Input (mouse/keyboard/controller)

    WINDOW DATA held in SLOT ARRAY, accessible via opaque handle ?? 

## + Graphics Layer
    Abstract common graphics API operations 
        resource creation (textures, buffers, shaders, pipelines, render passes)
        resource management/update
        submitting commands to GPU 
        
    Graphics API is written as an explicit pipeline ??

    INTERNAL RESOURCES are managed by implementation: 
        + shader handles 
        + texture handles 
        + buffer handles 

## + Audio Layer





## Ultilities: 
## + Immediate drawing Layer

## + Asset Manager Layer
    loading files ... 
