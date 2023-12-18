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

Access List (ACL): 
    have to understand the flow and topology of the network to setup this 

### FINAL REPORT STRUCTURE:
    I. Introduction 
    II. Implementation
    III. Conclusion
    Appendix
    (3 bang)
    1. Self-evaluation:
        Report / toi da 1
        Presentation / toi da 1
        Demo / 
        (Theo mo ta trong file tren course)

    2. Task Assignment
        bang: 
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
