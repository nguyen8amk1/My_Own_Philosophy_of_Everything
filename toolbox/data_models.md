# DATA MODELS

Entity Relationship Model: 
    2 primitives:
        + Entity Type (Object): -> An ABSTRACT concepts of something need to be represent in the DB
            -> Square 
            + Properties/Attributes:  
                -> Type of Attribute: 
                    + Single-Valued: (Kinda like a variable)
                    + Multi-Valued: (Kinda like javascript array, can contains various type)
                    + Composite: (Kinda like a struct in C)
                Keys: 
                    Define the uniqueness of an Entity 
                    -> Can have multiple keys 

            -> Entity: -> A CONCRETE value of the an Entity Type  


        + Relationship (Contraints/Morphism): 
            -> Oval 
            + Properties: 
                The Keys of the Connected Entities 
                Additional properties
                Contraints: 
                    2 relationship cardinality (minCurrent, maxOther):
                        left: (minA, maxB)
                        right: (minB, maxA)

            Note: 
                Relationship don't have direction -> cause the directionality of is implicitcally understood 
                    -> based on:
                        + the meaning of the Entity 
                        + cardinality constraints (e.g., one-to-many, many-to-many)


    -> Use to convert into Tables (Relation Based Physical Representation)

Relation (luoc do quan he): 
    ER -> LUOC DO QUAN HE -> SQL TABLE 
    Tan tu: quy tac dung de mo ta mot quan he (table)
        vd: THI (MASV, MAMH, LANTHI, DIEM)
            ||THI||: 
                moi sinh vien duoc phep thi mot mon nhieu lan, moi lan thi luu tru sinh vien nao thi mon gi ? lan thi thu may? diem bao nhieu? 

        Integrity contraints: 
            Defines the uniqueness of the an entity 
            Super key: can have multiple 
            Key: can have multiple 
            Primary key: only have 1 

        References:
            A references B when:
                A use some properties of B 
            -> Foreign Key: The property of B that references in A


Converting Logical Representation to Physical Representation (ER to Relation (table)): 
    CONVERSION from ER to Relation(table):
        The conversion will depends on cardinality contraints:
            with format: (maxLeft, maxRight)
                -> given 2 relationship cardinality (minCurrent, maxOther):
                    left: (minA, maxB)
                    right: (minB, maxA)
                    -> (maxB, maxA)

        (1, 1) => 2 ways:
            + Give B the key of A
            + Give A the key of B, Give B the key of A -> both ways 
        (1, n) => Give the 1's relation the key of n's relation
        (n, n) => Create a new relation with the name of the relationship that's connect Entities  
            contains:
                all the keys of the involved Entities 