# WEB DEVELOPMENT CONCEPTS (UIT)
notes from DO THI HUONG LAN PDF

## LAB3: 

## LAB4: STATE MANAGEMENT 
    Session
    Cookie
    Web storage 

    -> Co che luu tru du lieu 

### Cookie: 
    -> Doan van ban (text), ghi thong tin duoc tao ra ?? 
    -> LUU tren BROWSER nguoi dung 
    -> Thuong duoc TAO RA KHI:  
        + nguoi dung TRUY CAP 1 WEBSITE 
            -> Cookie se ghi nho: 
                + TEN DANG NHAP 
                + MAT KHAU 
                + TUY CHON NGUOI DUNG di kem 
    -> NHAN BIET NGUOI DUNG khi nguoi do truy cap 1 trang web 
    -> Thuong duoc DUNG: 
        + Luu tru TUY CHON RIENG cua tung USER 
        La 1 file nho duoc SERVER chi dinh luu tren CLIENT 

        -> **NOTE: THE COOKIE FIRST GET SNIPPED FROM THE SERVER SENT THROUGH THE RESPONSE
            -> it starts with the SERVER 

        -> @Question: Does the browser send all the cookies that it have to any particular server ?? 
            -> the browser will only send the cookie that associate with that specific domain   
            -> Not send the one that not related, since the cookie have the "domain id" in it 

    -> De SU DUNG Cookie thi BROWSER phai HO TRO, else you can't do shit :v 
    -> KHONG BI MAT KHI DONG UNG DUNG, ma PHU THUOC vao THOI GIAN SONG ma ban set cho no  
     

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
    -> Luu lai du lieu nguoi dung: SU DUNG WEBSITE 1 CACH TAM THOI
    -> Bat dau khi CLIENT GUI REQUEST DEN SERVER 
        -> TON TAI tu trang nay den trang khac (XUYEN SUOT) trong ung dung 
        -> chi KET THUC khi: 
            + het thoi gian timeout 
            + dong ung dung 
        
    -> GIA TRI cua SESSION duoc LUU TREN 1 FILE TREN SERVER 
    -> Co the tuy y quyet dinh xem thong tin nao nen luu tren session:  
        ** CHI NEN LUU TRU THONG TIN TAM THOI:
            + thong tin dang nhap 
            + thong tin san pham gio hang 

    -> Moi session duoc cap phat cho 1 ID duy nhat
        -> ket thuc va bat dau 1 phien moi -> duoc cap 1 ID khac 
    -> Sequence diagram: 
        1. Client: POST login: username + password 

        2. Server: Create session in DB
        3. Server: ATTACH the SESSIONID to the COOKIE and SEND it to the Client 

        4. Client: Send request with Cookie 

        5. Server: Get the sessionid from cookie, 
                   Look the DB for SESSION with matching SESSIONID 
        6. Server: Send RESPONSE to client 


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
    -> Co che LUU TRU DU LIEU tren BROWSER 
    -> Cho phep luu tru thong tin duoi dang key-value pairs
    -> 2 loai web storage: 
        + local storage 
        + session storage 
    -> Local storage: 
        -> Pham vi luu tru: 
            -> TON TAI VINH VIEN tru khi bi xoa boi nguoi dung 
        -> CHIA SE DU LIEU giua cac trang web:  
            -> Duoc chia se voi tat ca cac trang web o 1 domain cu the (Same-Origin Policy)
    -> Session storage: 
        -> Pham vi luu tru: 
            -> Luu tru trong suot PHIEN lam viec cua BROWSER, sau khi ket thuc phien (vd: close browser), sessionStorage se bi xoa 
        -> CHIA SE DU LIEU giua cac trang web:  
            -> Duoc CHIA SE giua cac trang in the SAME BROWSER WINDOW  
        API: 
            + setItem(key, value)
            + getItem(key)
            + removeItem(key)
            + clear()

    -> Thuong duoc su dung: 
        -> Can luu tru du lieu lon hon Cookie
        -> Khong can gui du lieu trong moi request 
        -> Thich hop de luu tru: 
            + CAI DAT nguoi dung (user setting)
            + TRANG THAI ung dung (app state ??)
            + du lieu CACHE 

        -> NOTE: khong luu thong tin nhay cam 

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

