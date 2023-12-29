# NETWORK SECURITY NT140 NOTES
tu tao public, private key roi gui len xac nhan 
thay vi de cho no tao tat ca roi minh dung
prime256v1
04: -> chia doi 1 nua x, 1 nua y
apache luu key va cert trong conf/ssl 
protocol + TLS = secure protocol

## Week 5: 
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

## Week 10: 
    routing table - doc tu phai qua trai 
    ICMP smurt attack: 
        ping broadcast
        gia danh ip cua nguoi khac 
        -> nguoi ta bi ddos ping 

        -> solution: chan ping broadcast 

    ICMP tien ich nhma phai han che 1 so tinh nang de tranh bi tan cong.

    Congestion control: Outdate, not used 

    Border routing bsp ???
    Cang len cao thi cang phuc tap (in NETWORKING MODEL)
    SDN

    Transport layer:
        + xac dinh phuong thuc truyen: tcp, udp, quic
        + identify sender, receiver

    Scan for port, have a list of port 
        -> attack the weak one

    Tai nguyen port la huu han -> het roi thi teo 

    How to kill a host: 
        heavy:
            + computation
            + payload
    
    Reverse path: kiem tra xem ip request co phai that khong  

    Doi vua phai 
    Mo limit 

    tan cong:
        icmp redirect -> ddos - spoof ip

## Week 12: 
    Filter at the application layer of the end point
    the link level:
        work using the ARP table (table of router's mac address)
            -> vulnerable if the ARP table is attack 

    P2P: done upload and download at the same time 
        -> acts as client and server at the same time

    Bug 
        + SOFTWARE: 
            if function want A but it done B
        + SECURITY: 
            if function want A but it done B and C
            vd: Rather than answer yes/no but it answer the correct answer as well 

    Session Hijacking: 

    2 Huong khai thac:
        Header -> cuop session
        Payload -> gui ma doc 

    Injection: 

    Login should have a separate page with their own url 
        -> user can check if the url is valid 

    Time-based token
    Clicked-based token

    Exceptional case: 
        Gmail: stole just token is not enough to login 
        -> Hidden input in the frontend 

    DNS: local dns is only a CACHE SERVER, and can be contaminated  
        2 types: 
            Authorative: store the original information of the url 
            Caching: 
                pros:
                    khong ton bang thong di ra ngoai 
                    tra loi nhanh

        but If you check using nslookup you will see that the Authorative is not atually Authorative, 
        it have higher level Authorative even :v

## Week 13: 
    2 types: 
        + A lot of attack related to HEADER 
            since header is use for session management  
        + Message is also attacked,
        since people use different 

    After authentication: 
        + Authorization
        + Session management 

    Where does local DNS located ?? 

    EXPLOIT the local DNS UPDATE MECHANISM 
        -> since localDNS is only save temp version of the mapping 

    if Authorative server get DDOS -> EVERYTHING is DOWN 

    CACHE POISONING ATTACK:  
        man in the middle attack
            spoofing DNS reply 

    Root DNS -> output: Top Level Domain server 
    TLD DNS -> output: Authorative server 

    DNSSEC 
    If the attacker sniff at the link between TLD and Local DNS 
        -> they can change the pointer to Fake Authorative server

    TLS Record Protocol 

## Week 14: 
    DNS Rebinding Attack (kha la cong phu):  
        loi dung 1 node trong lan de tan cong target 
        -> giai phap khong toi uu: keo dai thoi gian caching 

    Depth Defence:   
    Network secure protocols: 
        goals: 
            + Authentication: network nodes (hosts), application API (apps)
            + Key agreement; 
            + Cryptographic algorithm negotiation (ciphers, MAC)    

    Key agreement: 
        Diffie-hellman key exchange + extra (to prevent man-in-the-middle)

    Certification goals: 
        no la ai 
        giay chung nhan la gi 
        ai chung nhan 

    Network authentication API: 
        + static strings
        + dynamic tokens
        + User-delegate token
        + Attributed-based Access Control 

    API gateway: 
        
    3 nhom: 
        1 nhom xu ly nguoi dung 
        1 nhom xu ly thong tin 
        1 nhom ... 

    Covert channel attack: 
        dung 1 node khac de bypass qua 1 node khac trong mang lan        

    Noi luu giu public key = Trusted Domain 
        -> de bi tan cong 
        vd: kiem soat Trusted Domain  cho ki (dung nhu Windows)
        -> Phai Xac thuc de xem co quyen duoc luu hay khong, Xac thuc truoc khi luu 

    Secure: 
        Application + TLS: only hide header and payload of application level, not the lower one  
            -> the lowerone could still get attacked
        IP layer + Ipsec, VPN protocols: 
        Datalink layer + WEB, WPA, WPA2, WPA3: 

    VPN: 
        2 modes: 
            ternal mode: giau luon ip 
            transport mode: khong giau ip

        Them 1 layer/header de giao tiep voi ben ngoai 

    VPN trong LAN: 
    VPN de ket noi voi thiet bi noi bo. trong LAN

    Hardware = Legacy system 
        vd: ATM 

    SSH protocols:

PROJECT: 
sample web app: 
    links: https://github.com/alokyadav1/mern-todo-app

NOTE PRESENTATION: 
    + TAT CA SOLUTION KHI DUA RA PHAI NOI DUOC TINH UU VIET CUA NO 

    + Target: mo hinh dep roi -> lieu co dung mo hinh machine learning de bao ve tai san duoc khong ? 
    + Deploy dung duoc module moi quan trong

    "KHONG QUAN TRONG LA LAM CON DAO, MA DUNG CON DAO TOT CHO CONG VIEC",  NGUYEN NGOC TU 2023  

    Quan trong la KIEN TRUC HE THONG: 
        day la module 1, module 2 
            TUONG TAC vs nhau ntn 

    "THAY KHONG QUAN TAM EM LAM CAI GI: ... :v
    NHUNG MA IDEA, KIEN TRUC,... NO PHAI DUNG", NGUYEN NGOC TU 2023

    CLOUD, CLOUD, CLOUD, 
    CLOUD, CLOUD, CLOUD, 
    CLOUD, CLOUD, CLOUD, 

    HIEU SAU VE PLATFORM DEN TRIEN KHAI 
    
    "DAN SECURITY MA CAU THA LA NAT BET", NGUYEN NGOC TU 2023

    SECURITY ANALYTIC, ANALYSIS: 

    KHONG NOI VE FUNCTION,
    NOI VE Y NGHIA SECURITY, MO TA NHU THE NAO CHO NO CHAY    
    KIEN TRUC SECURITY != KIEN TRUC DEVOPS

    KIEN TRUC DEVS: 
        -> FUNCTIONS

    KIEN TRUC SECURITY: HIGH LEVEL 
        + component
        + tuong tac component
            -> lam sao tuy bien duoc de dat duoc target
        + data flow 

    LAM SAO DE THEO DOI DATA FLOW NHU THE NAO ?

    GIAI THICH MODULE GIAI QUYET VAN DE SECURITY NHU THE NAO ?
    MUON DUA MODULE VAO PHAI GIAI THICH MODULE TUONG TAC NHU THE NAO ?

