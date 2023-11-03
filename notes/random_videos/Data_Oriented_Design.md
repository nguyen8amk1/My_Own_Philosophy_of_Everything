# DATA ORIENTED DESIGN: INTRODUCTION
note from this video: https://www.youtube.com/watch?v=pvWRQwRvdPI&ab_channel=GetIntoGameDev

Keys: 
    using STRUCT OF ARRAYs
        -> have inline array of data, ALL THE DATA possibly need for the operations
        -> have a single call to perform all the work -> BATCHING all the work in 1 call 

        vd: an array in the struct contains all the properties data of the elements
        vd: pos = [x1, y1, z1, x2, y2, z2, ...]
        stride: 
            the number of elements of each entry (vd: 3 for (x1, y1, z1))
            -> 
                to get the index of the entry -> index(i) = stride *i (0<= i <= n)
                access each fields of the entry i -> field(j) = index(i) + j (0<= j < stride)

    rather than 
    using ARRAY OF STRUCTs 
        -> require to CALL METHODS of EACH of the ELEMENT of the array 
            pieces of required DATA are SCATTERED 
            when doing a unified operation
            vd: if array have 10 elements -> have to call the method on each element 10 times 