# QUAN TRI MANG TRONG 1 NOT NHAC
notes from course: https://www.youtube.com/watch?v=dwRgs6iviKQ&list=PLb-gZ71w7d24EJm4cu82AA1Uqil3qdjn7

## OSI model: 
    Application: 
        -> ESTABLISH CONNECTION between computers
    ...
    Transport: 
        -> Separate the message into packets 
    Network: 
        -> Setup the logical address (IP) of src, dest for the packets (port as well)
        -> Optimize the SENDING PATH using some routing algorithms (RIP, OSPF,...)
    Data Link: 
        -> "Threading" the packets sending process, each type of protocol have different paths
        -> Determine which packet goes which path and put the packet on the path 
    Physical: 
        -> The actual physical path (wired, wireless,...)

## NOTE: TCP/IP and OSI model actually represent different things :v
    OSI Model represent: 
        -> the actual "physical" flow of data through the networking modules 
        -> basically the U shape
        
    TCP/IP Model represent: 
        -> the logical flow of data between same level layers of 2 computers
        -> basically Parallel lines  
        

## TCP/IP model
    Application: 
        -> vd protocols: DNS, SSH, Telnet,...

    Transport: 
        -> vd protocols: TCP, UDP

    Network: 
        -> Setup the logical address (IP) of src, dest for the packets (port as well)
        -> Optimize the SENDING PATH using some routing algorithms (RIP, OSPF,...)
    Data Link: 
        -> "Threading" the packets sending process, each type of protocol have different paths
        -> Determine which packet goes which path and put the packet on the path 

    NOTE:  
        MAC address: an globally unique address for a network port 

-> Each layer of the model is an abstracted module
    -> Each layer have a lots of choices 
    -> You can have a concrete implementation as any combinations of the current technologies have 
    -> Each technology can be manufacture by any company 
    -> Everybody have their pieces in the big (networking) pie.  
    -> Basically it's a spanning tree of tech 
        Kinda like this:
            (Abstract) OSI Model: 
                + 1. (Abstract) Application
                    vd (Concrete): 
                        + telnet 
                        + gmail
                        ... 

                + 2. (Abstract) Transport 
                    vd (Concrete): 

                + 3. (Abstract) Network
                    vd (Concrete): 

                + 4. (Abstract) Data Link
                    vd (Concrete): 

                + 5. (Abstract) Physical: 
                    vd (Concrete): 

