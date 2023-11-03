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

    questions: 
        what is host-only ?? 
            ....
        what is NICs ?? 
            -> Network Interface Card 

        what is NAT ?? 
            ....  
