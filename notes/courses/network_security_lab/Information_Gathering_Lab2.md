# INFORMATION GATHERING 
"Cang co nhieu thong tin ve doi tuong, 
chung ta cang co them nhieu co hoi khai thac vao doi tuong."

## KIEN THUC NEN TANG:
### 2 loai THU THAP THONG TIN: 
    + Thu dong (Passive Information Gathering)
    + Chu dong (Active Information Gathering)

###  2 loai DU LIEU (cua Quy trinh thu thap thong tin): 
    + Du lieu mang: 
        vd: 
            + ten mien (public, private)
            + cac may chu 
            + day IP public/private 
            + bang dinh tuyen (routing table)
            + cac dich vu TCP va UDP 
            + Chung chi SSL
            + Cac port dang mo (opening port)

    + Thong tin lien quan den he dieu hanh: 
        + thong tin user 
        + he dieu hanh dang su dung 
        + banner ?? 

## THUC HANH: 
### 1. Thu thap thong tin thu dong (Passive Information Gathering): 
    -> hay con goi: OSINT 
        -> Qua trinh thu thap thong tin thong qua cac phuong tien cong cong.  
    -> 2 cach: 
        + 1. Khong tuong tac truc tiep voi doi tuong: 
            -> dua vao ket qua tu ben thu 3 
                khong truy cap bat ki he thong/may chu nao cua doi tuong.
            -> pros: 
                + giu duoc tinh bi mat ve hanh dong, y dinh cua minh  
            -> cons: 
                + ket qua tim kiem bi gioi han 

        + 2. Co tuong tac voi doi tuong (as a normal user)
            vd: 
                website cho dang ky tai khoan -> thuc hien dang ky tai khoan

            NOTE: 
                danh gia website de tim kiem lo hong, 
                KHONG NAM TRONG GIAI DOAN NAY 

    + Do tham Website (Website Reconnaissance): 
        -> Neu doi tuong co trien khai website. 
            -> Thu thap thong tin co ban bang cach 
                truy cap vao website cua doi tuong.

    + Whois Enumeration: 
        Whois la:
            + a DICH VU TCP, 
            + a Tool 
            + a Loai CSDL 

        -> Cung cap THONG TIN VE TEN MIEN: 
            + Name servers (dia chi DNS dang tro ve ten mien)
            + Registar (Nha quan ly ten mien:
                vd: 
                    + Namecheap
                    + Godaddy
                    + ...
                )
            + NGAY DANG KI ten mien
            + Ten nguoi dang ky ten mien

    + Google Hacking: 
        -> Su dung cac search engine de co the lay duoc:
            + THONG TIN 
            + LO HONG 
            cua cac Website CAU HINH SAI 
        + Tu khoa thong dung: 
            + site
            + filetype (or ext)
            + ky tu '-':
                -> de LOAI BO cac KET QUA tim kiem KHONG MONG MUON.
        -> For more keywords [Google Hacking Database](https://www.exploit-db.com/google-hacking-database) 

    + Netcraft: 
        ... 

    + Recon-ng: 
        ... 

    + Open-Source Code: 
        ... 

    + Shodan: 
        ... 

    + theHarvester: 
        ... 

    + Information Gathering Frameworks: 
        + OSINT Framework: 
            ... 
        + Malgeto: 
            ... 

### 2. Thu thap thong tin chu dong (Active Information Gathering)
    ... 
    + DNS Enumeration: 
        + Tuong tac voi may chu DNS: 
            ... 

        + Tra cuu tu dong(Automating Lookups): 
            ... 

        + Forward Lookup Brute Force: 
            ... 

        + Reverse Lookup Brute Force: 
            ... 

        + DNS Zone Transfers: 
            ... 

    + Port Scanning: 
        ... 
        + Port Scanning su dung Nmap: 
            + Stealth/SYN Scanning: 
                ... 

            + TCP Connect Scanning: 
                ... 

            + UDP Scanning: 
                ... 

            + Network Sweeping: 
                ... 

            + OS Fingerprinting: 
                ... 

            + Banner Grabbing/Service Enumeration: 
                ... 
                + Nmap Scripting Engine (NSE): 
                    ...

#### Cac cong cu co lien quan(den thu thap thong tin chu dong) co tren Kali Linux: 
    ... 
    + DNSRecon: 
        ... 

    + DNSEnum: 
        ... 
