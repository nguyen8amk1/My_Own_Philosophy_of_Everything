# INTRUSION DETECTION SYSTEM (IDS)

IDS: 
    Software that CHECKS a network or system for MALICIOUS ACTITIVIES or POLICY VIOLATIONs.
    -> Observes network traffic for malicious transactions
        and SENDS immediate ALERTS when it is observed. 

## 5 types: 
    + Network IDS (NIDS): 
        ...

    + Host IDS (HIDS): 
        ...

    + Protocol-based IDS (PIDS): 
        ...
    + Application Protocol-based IDS (APIDS): 
        ...

    + Hybrid ISD: 
        ...

## Detection methods: 
    + Signature-based Method:
        -> detects the attack on on the basis of the SPECIFIC PATTERNS (such as the number of bytes)
        -> easily detect patterns that already exist -> but hard to detect new malware 
    + Anomaly-based Method: 
        -> use maching learning to detect intrusion 
## IDS vs Firewall 
    + IDS: 
        detect INTRUSION once it HAS HAPPENED then signal alarm

    + Firewall: 
        looks OUTWARDLY for intrusions in order to stop them from happening 

# SNORT 
    is an Intrusion Prevention System (IPS) 
    uses a series of RULES that help define:
        + malicious network activity  
        + find packets that match against them -> generate alerts of users 

    can be Inline Deployment: 
        a network configuration where a device(vd: security appliance, network component)
        PLACED DIRECTLY IN THE DATA PATH of the network traffic 

    3 Usages:  
        + packet sniffer (like tcpdump)
        + packet logger (for network traffic debugging)
        + full-blown network intrusion prevention system 

    **Note: Have 3 sets of rules: 
        + Community (we're gonna use this) - free created by the Snort community. 
        + Registered rules - free created by Talos. 
        + Subscriber 

        -> you can write your own rules 

    Detection malicious traffic/attack by: 
        PATTERN MATCHING 
        
    When active:
       1. captures packets 
       2. reassembles them
       3. analyzes them 
       4. determines what need to be done to the packets based on PREDEFINED RULES.

    Snort has a LARGE AMMOUNT of RULE-SETS created by the community 
        -> useful to begin with 
    Snort rules are easy to write and understand 

    Version: 
        Snort 2: 
        Snort 3: 

    -> we will use Snort 2

    Rules: 
        what to do with packets 

    How Snort works: 
        ![How Snort works](./images/How%20Snort%20Works.jpg)
        basically:
            1. Capture packet through sniffing
            2. Preprocessor 
            3. Snort Detection Engine and Rule set
            4. Alarm logging
            5. Log file analysis 

        -> Snort can be both IPS or IDS ->  can either Detect or Prevent 
        if Snort is IPS -> place it on the outermost connection 
        if Snort is IDS -> place it on the switch  
        -> both are placed after the firewall but the IPS is closer to the firewall 


    ** Project: 
        Requirements: 
            + Basic: 
                INSTALL Snort on Windows/Linux and DETECT some network ATTACK (using DEFAULT RULES)

            + Advance: 
                Install a SEPARATE SERVER and DETECT THE ATTACK TO SERVER

            2 VMs: 
                1 server (2 NICs: NAT, host-only)
                1 client (host-only)

            -> Nang cap 10 diem: -> 3 VMs: 
                1 vulnerable server (2 NICs: NAT, host-only)
                1 Snort (2 NICs: NAT, host-only) ?? 
                1 hacking client (host-only)
    Configuration: 
        VM: 
            1. Vulnerable server (host-only, NAT) -> 2 NICs
            2. Snort server (host-only, NAT) -> 2 NICs 
                -> remember the MAC address of each NIC 
                -> ip range of the Snort server (local ip range)
                the subnet that the vulnerable server and the snort server live on 
            3. Attacker Client (NAT)

            -> Attacker -> Snort Server -> Vulnerable server

        Vulnerable server:
            + installation: 
            + config: 

        Snort: 
            installation: 
                -> Interface to listen to 
                -> subnet that the Snort live on

            configuration (in the config file): 
                -> ipvar HOME_NET ip_address/mask -> assign ip address to var HOME_NET
                -> rules: 
                    #include $RULE_PATH/**.rules
                    custom rules in "local.rules" file  
            start: 
                sudo snort -T -i <interface> -c <config_file>
            start and execute rule: 
                sudo snort -A console -q -i <interface> -c <config_file>

    mau bao cao do an: 
        https://www.studocu.com/vn/document/dai-hoc-quoc-gia-thanh-pho-ho-chi-minh/marx-lenin/mau-bao-cao-do-an-uit-mau-bao-caotieu-luan-cua-truong-dh-cntt/21126530

4 major components, which chained together to fulfill its various modes.
	+ Decoder:
		responsible for FORMING PACKETS to be used by the other components
        DETERMINING:
            + which underlying PROTOCOLS are 
            + location of data
            + size of data 
            of the Packets 
        it also check the anomalies in headers (such as invalid sizes) which may then cause it to generate alerts.
        
	+ Preprocessors:
        There components work as PLUGINS. 
        -> Arrange, modify packet data. 
        There are a lot of Preprocessor:
        ex: 
            HTTP Preprocessor: Handles and analyzes HTTP traffic,
            ARP Preprocessor: Monitors ARP packets

        Essentially: 
            try to help the detection engine by clearing some ambiguous information.
                Ex: 
                    + decode the URI's ->  reveal the actual content and make it easier for the detection engine to analyze and detect potential threats
                    + defragmenting packets ->  reconstructing the original packet content and making it easier to analyze for malicious activity

    + Detection Engine: 
        -> detect if ANY INTRUSION ACTIVITY EXISTS in a packet
        by chaining together sets of rules
        applying them to each packet
        If the packet matches a rule -> the specified action of that rule is taken

	+ Alert and Logging System: 
        If a packet is matched to a rule 
        -> the log and or alert will be generated 
        The message and contents of the alert can be configured through the configuration file. 

	+ Output Modules:  
        After an alert or log is generated, 
        it passes through the Output Modules component
        controlling the type of output generated
        uses a flexible plugin system
        ex: 
            This may include simply logging, or 
                                    logging to a database, 
                                    sending SNMP traps, 
                                    generating XML reports

ERROR: 
    Add Component of snort 
        https://www.google.com/search?q=how+snort+works+internally&sca_esv=579689770&tbm=isch&sxsrf=AM9HkKm2g_6OG0o4BFN6Yd_T3Gg4nMSJPA:1699234916762&source=lnms&sa=X&ved=2ahUKEwi0xOmsn66CAxU3slYBHZfXApEQ_AUoAnoECAEQBA&biw=1492&bih=740&dpr=1.25#imgrc=Vfucemqcu30ZYM
    Change the topology to match NIDS or HIDS 
    remove arrows and stuff  

Things to do: @Current, tonight  
    1. change the topology
	the network have to go through
	To NIDS
	If too hard -> HIDS 
    2. add the components description 
    3. move the how to write rules to configuration part 

FUCK IT: We're just gonna do the HIDS
THINGS TO DO TOMORROW: 
    Fix things in the report: (1h) 
        -> add the components of Snort in the report 
    Writing talking scripts for the demo part: (1h)
    record a demo video: @Mimic this video: https://www.youtube.com/watch?v=JQhhemHsUgc (3h)
        installation 
        configuration
        testing 
            ping test 
            ddos test 
            *basically like the video
    -> The whole morning 5h = 7h + 5h = 12h (wtf :V )

@@@@ask ChatGPT: 
    -> Given 3 vm, A, B, C 
    i want to A connect to C logically, but the request is redicted through B  
    basically the flow is gonna be like this: A -> B -> C


    Steps:
        Configure PORT FORWARDING on VM B: 

    Detect ping 
    Ping of death 

Port forwarding: 
    ...  
    Mapping: 
        + from (ip1, port1) 
        + to (ip2, port2)
    -> Allow:
        -> EXTERNAL devices to CONNECT to INTERNAL devices 
        -> ROUTE TRAFFIC to an IMMEDIATE SERVER  

    vd: 
        have a web server on your internal network (VM C) 
        that listens on port 80
        Setup port forwarding to allow external access
        When an external device connects to the router's IP on port 8080, the router forwards that connection to the internal IP of your web server on port 80.

## Presentation Script: 
### How to write a snort rule 
    As you may have heard before Snort intrusion detection system working based on Rules 
        So rules are the heart and sole of Snort 
    Let's learn how to write a rule 
    Using this rule template: 
    [action] [protocol] [source] [source_port] -> [destination] [destination_port] (options) 
    Let me explain: 
        First we have [action]: Specify the action to take when the rule matches. You have different action like: alert, drop, pass, log, ...  

        Next we have [protocol]: Indicates the protocol you want to match, the protocol the packet was sent in, such as: TCP, UDP, ICMP, ...  

        Source, Source Port: Define the source IP address, and Port, which are the information of the one who send the packet 

        Destination, destination port: Againt, it's Define the Destination IP address, and Port, which means our network information

        Lastly are some options: 
            the 2 most common are: 
                msg: the message you want to output when the rule match 
                sid: rule id to identify the rule, which suppose to be unique  

        Here is an example for a rule which detects incoming TCP traffic from an external network to the internal network on port 23, and the action when the snort Detects this behaviour is just alert:  
            alert tcp $EXTERNAL_NET any -> $HOME_NET 23 (msg: "Potential Telnet Access", sid:100001)

    Okay so now we know how to write a snort rule which detects a certain pattern of packet 
    But where do we apply those rules. 
    We apply the rules in a configuration file, located at /etc/snort/snort.conf 
    This config file determine how Snort should work on my machine 

### Demo video plan: (4h)
    The configuration will be in videos: 
        + Cat dat snort 
            su dung lenh: sudo apt install snort 
        + Vao file config cua snort, /etc/snort/snort.conf 
        + Show ip, interface may hien tai 
        + Thay doi bien $HOME_NET thanh subnet may hien tai 
        + Copy file config thanh file test.conf 
        + Xoa het lenh co san trong file test.conf 
        + Vao file rule viet lenh icmp
            alert icmp any any -> $HOME_NET any (msg:"Ai do dang ping toi"; sid:10000001;)
        + Chay snort 
            -> show hien tai co bao nhieu rule apply
            -> sudo snort -A console -u snort -g snort -i ens33 -c  /etc/snort/test_snort.conf
        + Ping vao victim tu kali 
        + Show the result 

        # Test sql injection 
        + Test the injection first 
        + Go to rule file, write the sql injection rule  
            -> alert tcp any any <> $HOME_NET any (msg: "Sql injection voi tu khoa or"; content:"or";nocase;sid:1;)
        + Run snort  
            -> sudo snort -A console -u snort -g snort -i ens33 -c  /etc/snort/test_snort.conf
        + Show the result  

THINGS TO DO TOMORROW: 
    How to write snort rule: 
        Add the rule template to the presentation slide 
    Demo video: 

questions: 
    what is host-only ??  ....
    what is NICs ?? 
        -> Network Interface Card 

    what is NAT ?? 
        ....  
