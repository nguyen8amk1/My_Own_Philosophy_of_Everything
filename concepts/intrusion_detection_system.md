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

    **Note: Have 2 sets of rules: 
        + Community (we're gonna use this)
        + Subscriber 

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
                1 server (2 NICs: NAT, host-only)
                1 Snort (2 NICs: NAT, host-only) ?? 
                1 client (host-only)

    questions: 
        what is host-only ?? 
            ....
        what is NICs ?? 
            -> Network Interface Card 

        what is NAT ?? 
            ....  


