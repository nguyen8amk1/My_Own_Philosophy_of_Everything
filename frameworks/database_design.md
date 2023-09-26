# DATABASE DESIGN

a database have 3 LEVELS OF REPRESENTATION: 
    -> Top down approach (from user to administrator/abstract to concrete)
    -> the composition is: View -> Logical -> Physical 
    + View 
        -> User view representation (only saw the interface)
            -> the most abstract/high level view 

    + Logical: 
        -> ABSTRACT reprentation  
        -> for database analyst -> define:
            + TYPE OF DATA to store
            + RELATIONSHIP between data 

    + Physical: 
        -> Storage level 
        -> CONCRETE representation

        + Questions to ask:
            + What data? 
            + How to store ? 
            + Where to store ? 
            + Indexing ? 
            + How query should works ?
                + sequentially 
                + randomly  
        -> for administrator 

DATABASE MODELS: 
    Tool to model database on Logical Level: 
        Defines: 
            + TYPE of Data 
            + Relationship between them 
        ....

    There are a lot of data models: 
        Mau tin oriented: 
            ....
        Object-oriented: 
            [Entity Relationship Model](../toolbox/data_models.md) 

    Basic flow:
        User Requirements (View representation) -> ER (Logical Representation) -> Relation ( along with Tan tu) (Physical Representation)
