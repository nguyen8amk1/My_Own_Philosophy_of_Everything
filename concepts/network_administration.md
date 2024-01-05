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

    -> If the MAC address don't have in the ARP table -> send BROADCAST (send to all interfaces)

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
            + 1. Client: 
                send DHCP discover (broadcast): ask for assign configs
            + 2. DHCP Server: 
                received DHCP discover -> send DHCP offer: provide configs 
            + 3. Client: 
                received DHCP offer -> send DHCP request: tell the DHCP Server that the configs was received
            + 4. DHCP Server: 
                received DHCP request -> send DHCP ACK: acknowledge that everything is configured (done)

    DHCP operations:
        2 types:
            + Router as DHCP Server: 
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

            + Router as DHCP relay agents: 
                refer the boardcast message to the single DHCP server 

NAT (Network Translation Address): 
    -> Convert public <-> private IP address 
        2 usages: 
            + multiple private ip clients can share 1 public ip when access the internet 
                -> internet sees all the different client with the same ip (with different ports):v 
                configurations:
            + Internet client can access private network using 1 static public ip 

    
VLAN: 
    Virtual LAN 
    all network devices are LOGICALLY connected (another level of abstraction :v)
    regardless of their PHYSICAL location

    Purpose: 
        + Improve security
        + Traffic management 
        + Make a network simpler ??
        + REDUCE THE SCOPE OF THE BROADCAST DOMAIN

        what is broadcast domain ?? 
            -> SET of all DEVICES receive the BROADCAST FRAMES (originate from any devices within the set)
        -> Isolate subnet through VLAN instead of using SWITCHES (multiple switches create huge boardcast domain)

    -> GROUP devices LOGICALLY, 
        -> even though physically all the devices are just in a single LAN, connected to a Switch 
        -> Group into different VLAN, and ISOLATE the PACKETS to each group
        -> Stuff from one VLAN CAN'T TALK to another VLAN 

    -> Can be done using VLAN supported SWITCH 
        -> done through dedicated ports for each group 
            vd: 16 ports switch 
                -> group 3 port for Group A, group 4 ports for Group B, ...

    -> InterVLAN routing (VLAN talking to each other)
        -> by default i can't :v 
        -> Using a Layer 3 device: 
            + Legacy: 
                cons: gioi han so luong VLAN co the giao tiep (cause dependence on Router interfaces count)
            + Router on a stick
                -> Switch connect to Router though a Trunk Port ? sub-interface ??  
            + Multi-layer switch 

Access Control List (ACL): 
    + Overview:  
        -> a sequential LIST of PERMIT/DENY STATEMENTS
        -> that CONTROL whether a router: 
            + forwards
            + drops
            packets based on INFORMATION found in the PACKET HEADER. 
        -> Located on: ROUTER: 

    + Operations:  
        -> the ROUTER - COMPARES the information within the packet 
        AGAINST each statement (in sequential order),
        if the packet match none of the statement -> remove (since there always a LAST STATEMENT an IMPLICIT DENY)  

        + 2 types of ACL OPERATIONS: 
            + Inbound: 
                -> Filter before routing (xu ly goi tin DI VAO router)
            + Outbound:
                -> Filter after routing (xu ly goi tin DI RA router)

    + 2 types of ACL: 
        + standard: 
            -> filter IP packets based on: SOURCE ADDRESS only 
            -> Located: near desitnation
                -> because: ...

        + extended: 
            -> filter IP packets based on: 
                + SOURCE and DESTINATION address (in IP Header)
                + PROTOCOL type/number
                + Source and Destination TCP/UDP - PORT NUMBER (in TCP/UDP header)
            -> Located: near desitnation
                -> because: ...
    One ACL per:
        + protocol 
        + direction (inbound, outbound) 
        + interface 

    NOTE: have to understand the flow and topology of the network to setup this 

### Wildcard mask in ACL: 
    + Definition: 
        -> a 32 bit string 
        -> used by router 
        -> determine: which bits of the address to examine for a match.
            0: match 
            1: ignore 
    + Example: 
        ...

    + Keyword: 
        + "host": = 0.0.0.0 mask (check all bits)
        + "any":  = 255.255.255.255 mask (ignore all bits)

    + Standard ACL Syntax: 
        + DEFINE standard ACL rule: 
            -> Router(config)# access-list <access-list-number> {deny | permit | remark } source [source-wildcard][log]
            trong do:
                + access-list-number: 1-99 or 1300-1999
                + source: source IP need to match 

        + Apply ACL to INTERFACE: 
            -> Router(config)# interface g0/0/0
            -> Router(config-if)# ip access-group access-list-number { in | out } 

        + REMOVE ACL: 
                no access-list <access-list-number> 
                
    + Extended ACL Syntax: 
        + DEFINE Extended ACL rule: 
            -> Router(config)# access-list <access-list-number> {deny | permit | remark } 
            source     [source-wildcard]      [Operator operand] [port port-number or name] 
            desination [destination-wildcard] [Operator operand] [port port-number or name] 
            [established] [log]

            trong do:
                + access-list-number: 1-99 or 1300-1999
                + source: source IP need to match 
                + destination: destination IP need to match 
                + Operator: lt(less than), gt(greater than), eq(equal)
                    -> so sanh cac port 

        + Apply ACL to INTERFACE: 
            -> Router(config)# interface g0/0/0
            -> Router(config-if)# ip access-group access-list-number { in | out } 

        + REMOVE ACL: 
                no access-list <access-list-number> 
                

### FINAL REPORT STRUCTURE:
    I. Introduction 
    II. Implementation
    III. Conclusion

    Appendix
    1. Self-evaluation:
        Report / toi da 1
        Presentation / toi da 1
        Demo / 
        (Theo mo ta trong file tren course)

    2. Task Assignment
        Member, Task, %

    3. Questions and Answers
        Tra loi cac cau hoi cua cac nhom khac hoi :v

    Chia loai de tai: 
        + Service: trien khai dich vu cho nguoi dung tren server 
        (vd: mail server, application server)     
            vd: Web:
                + local server
                + cloud

            vd: File Server: 
                + NFS
                + SMB
                + FTP

        + Management: 
            + vd: ADDS (ACTIVE DIRECTORY DOMAIN SERVICE): he thong PHAN CAP quan li cac may cung join vao cung 1 domain 
                +  

        + Monitor: 
            + vd: Nagios, Zabbix, Wazuh:

        + Access Control: 
            + vd: IPtable:
                doc phan nao cua goi tin de 
            + vd: Squid Proxy / Application Gateway
                doc du lieu o tang ?? 

        + SECURITY: SNORT 
            Dua tren cac signature nao ??  

        Reverse Proxy: 
            tiep nhan request (nhan ve)
        Forward Proxy: 
            chuyen tiep request (gui di)



## ON TAP: 
    link: https://thu4n.dev/posts/network-admin-review/?fbclid=IwAR1iGGU9MW0wQQCmI0WFpGq-h5bmCHjf3ABE77EFRTyZWSQhAAS7DnV2h_Y

### IP addresses: 
    + Static: 
        -> ip addresses that is MANUALLY CONFIGURED 
            -> does not change 
            -> remain constant unless manually modified. 
    + Dynamic: 
        -> ip addresses that is AUTOMATICALLY ASSIGNED by a DHCP server.  
            -> change every time the device connect to the network (or at regular interval)
### Routing: 
    + Static: 
        -> ROUTING INFORMATION on the router's table is MANUALLY CONFIGURED 
        -> does not change unless an administrator modified it 
    + Dynamic: 
        -> ROUTING INFORMATION on the router's table is AUTOMATICALLY UPDATED based on network conditions. 
        -> Dynamic routing protocols: 
            + RIP (Routing information protocol)
            + OSPF 
            + BGP

### CISCO CLI: 
    + EXEC mode: 
        + user mode: 
            + Prompt: Router>
            + Access: Limited access for BASIC MONITORING COMMANDS.
            + Command to Enter: Router>
            -> Available commands: 
                + show
                + ping
                + telnet

        + privilege mode: 
            + Prompt: Router#
            + Access: Provides ACCESS TO ALL ROUTER COMMANDS, INCLUDING CONFIGURATION COMMANDS.
            + Command to Enter: Router> enable
            -> Available commands: 
                + configure terminal
                + show running-config
                + copy running-config startup-config

    + CONFIGURATION mode: 
        + global mode: 
            + Prompt: Router(config)#
            + Access: Allows configuration of GLOBAL PARAMETERS.
            + Command to Enter: 
                + Router# configure terminal 
                    or
                + Router# conf t

            -> Available commands: 
                + interface
                + hostname
                + ip route

        + interface mode: 
            + Prompt: Router(config-if)#
            + Access: Allows configuration of INTERFACE-SPECIFIC PARAMETERS.
            + Command to Enter: Router(config)# interface interface_type interface_number
            -> Available commands: 
                + ip address
                + no shutdown
                + exit

        + router mode: 
            + Prompt: Router(config-router)#
            + Access: Allows configuration of ROUTING PROTOCOLS.
            + Command to Enter: Various, e.g., Router(config)# router rip

            -> Available commands: 
                + router rip
                + version
                + network

        + line mode: 
            + Prompt: Router(config-line)#
            + Access: Allows configuration of CONSOLE, TERMINAL, OR AUXILIARY LINES.
            + Command to Enter: Router(config)# line console 0

            -> Available commands: 
                + password
                + login
                + exit

        + service mode: 
            + Prompt: Router(config-service)#
            + Access: Allows configuration of SERVICES such as DHCP or NAT.
            + Command to Enter: Router(config)# service dhcp

            -> Available commands: 
                + service dhcp
                + ip nat inside
                + exit

### Router configuration snippet: 
    Router> enable  
        -> (elevates your access level from User EXEC Mode to Privileged Exec Mode)
        -> allow execute Privileged commands.

    Router# configure terminal
        -> enter global configuration mode 

    Router(config)# interface GigabitEthernet0/0
        ->  enters the configuration mode for the specified interface (GigabitEthernet0/0).

    Router(config-if)# ip address 192.168.1.1 255.255.255.0
        -> assigns an IP address (192.168.1.1) and subnet mask (255.255.255.0) to the interface
        -> CRUCIAL FOR ENABLING COMMUNICATION ON THE NETWORK
        -> Assign the GATEWAY ip

    Router(config-if)# no shut 
        -> enable the interface 

    Router(config-if)# exit
        -> return to previous mode 

    Router(config)# router rip
        -> enters the configuration mode for the RIP routing protocol. 
        This is where you can configure RIP-specific settings.

    Router(config-router)# version 2
        -> specifies that the router should use RIPv2

    Router(config-router)# network 192.168.1.0
        -> includes the specified network (192.168.1.0) in RIP advertisements
        -> tells the router to participate in RIP routing for this network.

    Router(config-router)# exit

    Router(config)# exit

    Router# write memory
        -> saves the configuration changes to the router's memory, ensuring that they persist after a reboot


### Show commands: 
    + show running-config [common]
        -> displays the CURRENT ACTIVE CONFIGURATION of the router.

    + show ip interface brief [common]
        -> provides a summary of the STATUS and IP ADDRESSES of all interfaces on the router.

        vd: 
            Router# show ip interface brief

                Interface           IP-Address   OK? Method  Status                 Protocol

                GigabitEthernet0/0  192.168.1.1  YES manual  up                     up
                GigabitEthernet0/1  unassigned   YES unset   administratively down  down
                Serial0/0/0         10.0.0.1     YES manual  up                     up
                Serial0/0/1         172.16.1.1   YES manual  up                     up

            Columns:
                + Interface:    
                    -> name of interface

                + IP-Address: 
                    -> the IP ADDRESS assigned to the interface. 
                    If unassigned, it shows as UNASSIGNED.

                + OK?: 
                    -> Shows whether the IP address is VALID and CORRECTLY CONFIGURED

                + Status: 
                    -> Specifies the method used to assign the IP address. 
                    It can be MANUAL (configured manually) or UNSET (not configured).

                + Protocol: 
                    -> layer 3 protocol STATE of the INTERFACE. (can be up or down)

    + show ip route [common]
        -> displays the router's ROUTING TABLE, showing the routes it knows and the next-hop information.
        vd: 
            Codes: C - connected, S - static, O - OSPF, R - RIP, M - mobile, B - BGP

            Gateway of last resort is 192.168.1.254 to network 0.0.0.0

            C    192.168.1.0/24 is directly connected, GigabitEthernet0/0
                -> The router has a directly connected network 192.168.1.0/24 on GigabitEthernet0/0.

            O    10.0.0.0/8 [110/2] via 10.0.0.1, Serial0/0/0
                -> There is an OSPF route to network 10.0.0.0/8 with a next-hop of 10.0.0.1 via Serial0/0/0.


    + show protocols [common]
        -> displays information about the configured ROUTING PROTOCOLS and their status.
        vd: 
            Routing Protocol is "ospf 1"
              Outgoing update filter list for all interfaces is not set
              Incoming update filter list for all interfaces is not set

                -> OSPF with process ID 1 is configured. There are no update filter lists configured.

    + show access-lists [common]
        -> displays the configured ACCESS CONTROL LISTS (ACLs) ON THE ROUTER.
        vd: 
            Standard IP access list 1
              10 deny 192.168.2.0 0.0.0.255
              20 permit any
        
            -> Access list 1 DENIES traffic from the 192.168.2.0/24 network and PERMITS ALL OTHER TRAFFIC.
            
    + show startup-config
        -> displays the SAVED CONFIGURATION that will be USED on the NEXT ROUTER REBOOT.


    + show version
        -> provides information about the ROUTER'S HARDWARE, SOFTWARE VERSION, and CONFIGURATION REGISTER.

    + show interfaces
        -> detailed information about the status and configuration of all interfaces on the router.

    + show history
        -> displays the command history, showing the commands entered during the current session

    + show clock
        -> displays the current date and time on the router.

    + show users
        -> displays information about USERS CURRENTLY LOGGED IN to the router.


    + show cdp neighbors
        ->  displays information about neighboring devices discovered through Cisco Discovery Protocol (CDP).

NOTE: 
    RIP and OSPF are just 2 dynamic routing protocol
    each have their own pros, cons 
    
    Troubleshooting flow: 
        + check show protocols
            -> check the protocols status on router, 
                the protocol currently configured on that router
                the INTERFACE  using that protocol
        + check show running 
            -> if the commands have been used to get to that state
        
### SWITCHING and VLAN
    Switch level 2 CANNOT FORWARD traffic between VLANs 
    without the assistance of a router. 
    

    Inter-VLAN routing: a process from VLAN to VLAN, using a ROUTER.  

    3 types of Inter-VLAN routing: 
        + Legacy 
                = router + (switch + n vlans)
                    -> n vlans -> n router interfaces 
            -> cons: have router scaling problem when want to add more vlans -> need more interface on router (can't scale well )
            commands: 
                + 1. Create VLAN on switch: 
                    -> vlan ID 
                    S1(config)# vlan 10 
                    S1(config)# vlan 20 

                + 2. Assign the switch port to VLAN: 
                    S1(config)# interface f0/0
                    S1(config-if)# switchport mode access 
                    S1(config-if)# switchport access vlan 10 

                    S1(config)# interface g0/1
                    S1(config-if)# switchport mode access 
                    S1(config-if)# switchport access vlan 10 
                    -> the switch is 
                        connect to vlan 10 on interface f0/0 
                        connect to router on interface g0/1

                + 3. Assign the IP (default gateway) on router: 
                    R1(config)# interface g0/0/0
                    R1(config-if)# ip add 192.168.10.1 255.255.255.0
                    R1(config-if)# no shut
                    
                    
        + Router-on-a-stick
            -> n vlans -> 1 router main interface (like a stick :v)

            commands: 
                + 1. Create VLAN on switch: 
                    -> vlan ID 
                    S1(config)# vlan 10 
                    S1(config)# vlan 20 

                + 2. Assign the switch port to VLAN: 
                    S1(config)# interface f0/0
                    S1(config-if)# switchport mode access 
                    S1(config-if)# switchport access vlan 10 
                    NOTE: 
                        not config the interface connect between router and vlan 

                + 3. Configure TRUNK interface
                    S1(config)# interface g0/1
                    S1(config-f)# switchport mode trunk

                + 4. Configure sub-interface on ROUTER
                    R1(config)# interface g0/0/0
                    R1(config-if)# no shut
                        -> open the interface

                    R1(config-if)# interface g0/0/0.10
                        -> create sub-interface
                    R1(config-if)# encapsulation dot1q 10
                        -> IMPORTANT: define VLAN TAG 
                    R1(config-if)# ip add 192.168.10.1 255.255.255.0
                                            
                

            main interface has n sub-interface: 
                each for 1 vlan 
                -> need VLAN TAG (SWITCH and ROUTER is gonna do the TAGGING, UNTAGGING)
            vd: 
                main interface: G0/0/0
                    sub-interface: G0/0/0.10
                    sub-interface: G0/0/0.20
            
            -> cons: have switch scaling problem (since there is only 1 connection to the router)

        + Multi-layer Switch
            -> can work on both layer 2, 3 have VIRTUAL INTERFACE 
            commands: 
                + 1. Create VLAN 
                    SWL3(config)# vlan 10 
                    SWL3(config)# vlan 20 

                + 2. Configure trunk interface
                    SWL3(config)# interface g0/0/0
                    SWL3(config)# switchport mode trunk

                + 3. Enable routing on MultilayerSwitch
                    SWL3(config)# ip routing

                + 4. Configure INTERFACE on ROUTER
                    SWL3(config)# interface vlan10
                    SWL3(config-if)# ip add 192.168.10.1 255.255.255.0
                    SWL3(config-if)# no shut

                    SWL3(config)# interface vlan20
                    SWL3(config-if)# ip add 192.168.20.1 255.255.255.0
                    SWL3(config-if)# no shut

        NOTE: 
            create tat ca vlan, mac du vlan do khong truc tiep ket noi voi switch 

### "Show command": 
    + show vlan 
        -> show vlan ports on switch 
