# PROCEDURE OF ALGORITHM ANALYSIS 
Try to apply the [Abstraction (Remove Hooks)](./how_to_learn_and_apply_concepts.md) to actually deduce a general procedure to analyse abitrary algorithms
2 types of algorithms:
    non-recursion 
    recursion 
    -> each have their own set of processes  

Non-recursion: 
    Different Concrete procedures of analysis 
        1. 
        2. 
        3. 

    -> 
        Main procedure: 
            + Boxing 
            ....


        Clearly explained the details of Objects: 
            delta_i: 
                the WORK COUNT OF THE LOOP at that specific i (cause the behaviour of delta_i is depend on i)
            range of i in sum: 
                the range of values of i that actually have delta_i works
                -> since the the whole range of i might not all fit the condition of delta_i 
                -> need to EXTRACT THE ACTUAL RANGE OF WORK 

            the count of how many i = how many times the delta_i gets called:   
                ....

            -> Extract and remember the Relation/Pattern between them: 
                Relation: 
                    ....

Recursion: 
    have 4 approaches to analyze, each have their own pros, cons:
        + Backward substitution (Truy hoi/thay the)
            steps: 
                1. Lap phuong trinh de quy 
                2. Backward substitution -> quy luat 
                3. Ket luan:
                    -> Qua trinh dung lai khi ? 
                    -> i = ? -> the i vao quy luat -> phuong trinh cuoi cung 
            pros: 
            cons: 
                can only solve 1 TYPE of T(), even though it can be sum up, but only 1 type 
                vd: can be only T(n-1), or T(n-2), but CAN'T BE BOTH 

        + Characteristic equation (Phuong trinh dac trung)
            -> a COMBINATION TRICKS to RECORD a bunch of NUMBERS 
            Steps: 
                1. Lap phuong trinh de quy 
                2. Dua ve 1 ve = 0 
                    1. Dat X^n = T(n) -> The vao pt = 0
                    2. Rut X^n_nho_nhat ra -> Phuong trinh co so mu 
                    -> Phuong trinh bac k cua pt dac trung (phuong trinh co so mu)
                3. Tim NGHIEM cua phuong trinh co so mu
                4. Xu li theo nghiem boi va nghiem don
                5. Dung T(0), T(1),... de tim ket qua chinh xac cua C1, C2, C3,...

            pros: 
                + can solve many type of T 
            cons: 
                + can only solve multiple if in a specific sequence/format: 
                    a0T(n) + a1T(n-1) + ... + ak(n-k) = 0

        + Generating function (Ham sinh)
            Steps:
                ...
            pros: 
            cons: 

        + Guessing and Induction (Doan nghiem va quy nap)
            pros: 
            cons: 

## Big O Notation  
solving frameworks 
Proving things  