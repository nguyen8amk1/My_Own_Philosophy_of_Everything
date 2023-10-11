# NETWORK ADMINISTRATION 
MAC: 
    physical address 
IP: 
    logical address  

Switch: 
    PLUG and PLAY device - no need configurations 
    use MAC address
    automatically learned default gateway MAC address (when first need to reach for outside subnet devices)
    MAC address changes when travel though each subnet

    ARP table: is blank when first use
        -> first request will be timed out (for the switch to find the dest MAC address)

Router: 
    use IP address

Default gateway: 
    a router might have a lot of interface
    The ip of the interface that connect to the subnet 
        -> the DEFAULT GATEWAY of the devices in the subnet = the IP OF THE INTERFACE that connect to the subnet 

DHCP: 
    a protocol
    DYNAMICALLY assign:
        + IP address 
        + subnet mask 
        + default gateway 
        + DNS server 
    -> for new device which join network

    DHCP protocol handshake ?? 
        Steps: 
            Client: 
                send DHCP discover (broadcast): ask for assign configs
            DHCP Server: 
                received DHCP discover -> send DHCP offer: provide configs 
            Client: 
                received DHCP offer -> send DHCP request: tell the DHCP Server that the configs was received
            DHCP Server: 
                received DHCP request -> send DHCP ACK: acknowledge that everything is configured (done)

    DHCP operations:
        2 types:
            Router as DHCP Server: 
                router receive the message and act as the DCHP server 

                -> configuration commands:
                1. EXCLUDE THE IP of the devices that use static ip -> prevent DHCP send an ALREADY USED STATIC IP (vd: router ip, static ip server,...)
                    vd: ip dhcp excluded-address 192.168.1.1

                2. define ips pool (create a pool of ip addresses) with a name
                    vd: ip dhcp pool NET10

                3. define the network address (the range) in which the dhcp is gonna generate from 
                    vd: network 192.168.1.0 255.255.255.0

                4. set default gateway
                    vd: default-router 192.168.1.1

                5. set the actual dns server ip address 
                    vd: dns-server 209.165.200.225

            Router as DHCP relay agents: 
                refer the boardcast message to the single DHCP server 

NAT (Network Translation Address): 
    Convert public <-> private IP address 
        2 usages: 
            -> multiple private ip clients can share 1 public ip when access the internet 
                -> internet sees all the different client with the same ip (with different ports):v 
                configurations:

            
            -> Internet client can access private network using 1 static public ip 