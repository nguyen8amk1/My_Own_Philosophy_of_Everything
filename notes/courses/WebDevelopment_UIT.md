# WEB DEVELOPMENT CONCEPTS (UIT)
notes from DO THI HUONG LAN PDF

## Lab4: State Storing 
    Session
    Cookie
    Web storage 

    -> Co che luu tru du lieu 

### Cookie: 
    + PHAM VI luu tru: 
        -> luu tru du lieu ca 2 PHIA: client, server
        -> duoc GUI QUA LAI giua client, server trong moi request, response

    + KICH THUOC luu tru: 
        4KB limit   

    + THOI GIAN ton tai: 
        Co the duoc thiet lap de: 
            + TON TAI trong 1 KHOANG THOI GIAN CU THE
            + Chi TON TAI trong 1 PHIEN cua lam viec cua BROWSER

    + TRUY CAP du lieu: 
        Ca CLIENT, SERVER deu co the truy cap 

    + AN TOAN bao mat: 
        Co the:
        + Bi THAY DOI boi nguoi dung (Cross-site scripting, CSRF)
        + Bi DANH CAP 

    + MUC DICH: 
        Luu tru: 
            + THONG TIN DANG NHAP 
            + TUY CHON nguoi dung (small)

### Session: 
    + PHAM VI luu tru: 
        -> chi LUU tren SERVER
        -> SERVER gan SESSIONID trong COOKIE -> XAC DINH PHIEN LAM VIEC 

    + KICH THUOC luu tru: 
        Khong gioi han cu the, tuy theo may chu host server 

    + THOI GIAN ton tai: 
        Den khi:
            + nguoi dung DANG XUAT
            + dong BROWSER

    + TRUY CAP du lieu: 
        Du lieu CHI CO THE duoc TRUY CAP o SERVER 
        -> tuy nhien SESSIONID duoc su dung de XAC DINH PHIEN tuong ung cua CLIENT 

    + AN TOAN bao mat: 
        AN TOAN HON so voi COOKIE vi DU LIEU duoc LUU o SERVER 

    + MUC DICH: 
        Luu tru: 
            + THONG TIN PHIEN LAM VIEC @Question: thong tin phien lam viec ?? 
                vd: Trang thai dang nhap (Login state??)

### Web storage: 
    + PHAM VI luu tru: 
        -> Chi LUU phia CLIENT
        -> KHONG duoc gui toi SERVER trong moi request 

    + KICH THUOC luu tru: 
        5-10MB  cho MOI TRANG WEB 

    + THOI GIAN ton tai: 
        + Vinh vien
        + THEO CAU HINH Cu the 

    + TRUY CAP du lieu: 
        Chi co the TRUY CAP o phia CLIENT 

    + AN TOAN bao mat: 
        Du lieu co the bi thay doi nguoi dung 
        NHUNG phai thong qua 1 so BIEN PHAP BAO MAT nhat dinh nhu: Same-Origin Policy, ...

    + MUC DICH: 
        Luu tru: 
            + du lieu lon hon (large data),
            need quick interaction from client  

