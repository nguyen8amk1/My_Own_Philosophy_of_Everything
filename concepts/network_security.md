# NETWORK SECURITY NT140 NOTES
tu tao public, private key roi gui len xac nhan 
thay vi de cho no tao tat ca roi minh dung
prime256v1
04: -> chia doi 1 nua x, 1 nua y
apache luu key va cert trong conf/ssl 
protocol + TLS = secure protocol

Week 5: 
    What can be sniffed ?? 
        + Unencrypted Data
        + Metadata
        + Session Token
        + Network Topology 

    VPN encrypt in  lower level: 
        -> device to device, rather than end to end  

    TLS works on application layer

    IMPORTANT: Data flow ?? 

    Raw-Socket (Interception Point, between network and link layer): no modification to the packet, just goes in and out, nothing changed  
    Higher-Level-Socket: 

    CAN'T SPOOF ON HIGH LEVEL -> ALWAYS WORK WITH RAW PACKET
        -> work straight with ring-buffer of the network card 
        -> SPOOF HAVE TO WORK WITH RAW SOCKET, sniff doesn't

    Works with C -> easily work with raw socket 
    -> 2 tool: sniff, spoof 
    
    IF BYPASS THE KERNEL -> HAVE TO DO ALL THE WORK OF PROTOCOL STACK (the work of OS)