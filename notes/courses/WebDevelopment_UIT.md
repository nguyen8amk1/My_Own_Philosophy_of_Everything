# WEB DEVELOPMENT CONCEPTS (UIT)
notes from DO THI HUONG LAN PDF

## LAB3: 
    ... 

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

## LAB5: AJAX RESTFUL API

### AJAX: Asynchronous Javascript and XML 
    -> NOT a PROGRAMMING LANGUAGE or TOOL 
    A METHOD: 
        to:
            + TRAO DOI DU LIEU voi SERVER 
            + CAP NHAT cac phan cua trang web 

            ma KHONG CAN TAI LAI TOAN BO TRANG 

    1. Co che hoat dong:         
        1. Browser:  
            Create an event: 
                + CREATE an XMLHttpRequest object 
                + SEND HTTPRequest

        2. Server:  
            + PROCESS the HTTPRequest
            + SEND the reponse back to the BROWSER
            
        3. Browser:  
            + PROCESS the output value 
            + UPDATE the web content 
    
    2. Loi ich: 
        + Callback: 
            ... ?? 
        + Asynchronous calls:
            ... ??

        + Than thien nguoi dung:
            Toc do nhanh hon
        + Tang toc do: 
            ... 

    3. Cac cong nghe AJAX: 
        Ajax KHONG phai la 1 CONG NGHE, ma la 1 NHOM CONG NGHE lien quan den nhau, bao gom: 
            + HTML/XHTML and CSS
            + DOM
            + XML and JSON
            + XMLHttpRequest (XHR): 
            + Javascript

        NOTE: 
            + XMLHttpRequest (XHR): 
                -> an API that could be used through javascript, VBScripts and other languages,... 
                -> giao tiep khong dong bo giua CLIENT and SERVER
                it does: 
                    + SEND du lieu tu CLIENT to SERVER in the BACKGROUND
                    + RECEIVE data from SERVER
                    + UPDATE the website WITHOUT RESTART the website 

    4. Doi tuong XMLHttpRequest trong AJAX: 
        ... 

### REST API: 
    1. Khai niem: 
        REST (Repretational state transfer): 
            mot dang CHUYEN DOI CAU TRUC DU LIEU ?? 
            mot kieu KIEN TRUC viet API 

            use HTTP to COMMUNICATE  

        RESTful API: 
            -> a STANDARD use for DESIGN API that use for RESOURCE MANAGEMENT 
            -> **CHUC NANG QUAN TRONG NHAT: 
                + QUY DINH CACH:
                    + SU DUNG HTTP METHODs (vd: GET, POST, UPDATE, DELETE,...) 
                    + DINH DANG URL
            

    2. Resource: 
        Quan ly Resource: 
            bao gom 4 TAC VU chinh: 
                + CREATE a new Resource 
                + READ a Resource 
                + UPDATE a Resource 
                + DELETE a Resource 

            Co rat NHIEU CACH KHAC NHAU de 1 website THUC HIEN 4 tac vu tren: 
            vd: mot trang web chay duoi ten mien: http://my-blog.xyz 
                -> xem noi dung bai viet voi ID la 123, co the lam theo 1 trong cac cach sau: 
                + http://my-blog.xyz/posts?id=123, method: GET
                + http://my-blog.xyz/posts/123, method: GET
                + http://my-blog.xyz/action=view_post&id=123, method: GET
                + http://my-blog.xyz/view_post&id=123, method: GET

                + http://my-blog.xyz/posts?id=123, method: POST
                + http://my-blog.xyz/posts/123, method: POST
                ... 
        Da THONG NHAT cac TIEU CHUAN khac nhau de thuc hien viec QUAN LY RESOURCE. 
            -> Tieu chuan nay duc goi la Web API/HTTP API, thong nhat viec quan ly cac resource cua web.  
            -> RESTful la mot trong cac Web API duoc su dung pho bien hien nay. ??

            **PHAN LOP HE THONG: 
                -> trong he thong REST
                CHIA TACH thanh phan he thong theo tung LAYERS

                Each layer only:
                    + USE the layer DIRECTLY BELLOW IT 
                    + COMMUNICATE with the layer DIRECTLY ON TOP of it 

    3. Uu diem cua REST: 
        + **REST URL:
                REPRESENT: RESOURCE
                NOT ACTION 

        + REST FOCUS ON RESOURCE cua he thong  

    TODO: DOING THE THING: 
        yc1: 
            + Write a RESTFUL api for a TODO list app 
                with CREATE, READ, UPDATE, DELETE
            Detail: 
                API Endpoints:
                    + (READ) List all tasks:
                        Endpoint: GET /tasks
                        Description: Retrieve a list of all tasks.

                    + (READ) Get a single task:
                        Endpoint: GET /tasks/{taskId}
                        Description: Retrieve details of a specific task using its ID.

                    + CREATE a new task:
                        Endpoint: POST /tasks
                        Description: Create a new task.
                        Request Body: JSON with task details (e.g., title, description, due date).

                    + UPDATE a task:
                        Endpoint: PUT /tasks/{taskId}
                        Description: Update an existing task identified by its ID.
                        Request Body: JSON with updated task details.

                    + DELETE a task:
                        Endpoint: DELETE /tasks/{taskId}
                        Description: Delete a task using its ID.

        yc2: 
            Choose 3 with UI: 
            + Xu ly form dang nhap 
                use the previous dang nhap and move the checking to the backend 
                that's it :v 
            + Kiem tra su ton tai cua tai khoan
                use the previous dang nhap and move the checking to the backend 
                that's it :v 
            + Load more, Lazy load 

            Step: 
                1. Step create an account, with serverside checking 
                2. Login, with serverside checking
                3. Go into a page with tons of picture waiting to be loaded :v 

## LAB6: WEB APPLICATION DEPLOYMENT 

### MO HINH TRIEN KHAI ung dung web 

#### Mo hinh chung 
steps: 

    1. Browser: SEND REQUEST to WEB SERVER 

    2. Web Server: SEND REQUEST data to WEB APPLICATION

    3. Web Application: 
        have 3 INPUTS: 
            + File system: HTML Templates  
            + Database: data 
            + Web Server: Request Data (vd: URL Encoding, GET/POST data, Cookies)

    4. Web Application: SEND HTML (compose from the 3 inputs) back to the WEB SERVER 
    5. Web Server: SEND RESPONSE to the BROWSER
        The reponse have 2 INPUTS: 
            + Web Application: HTML

            + File system: STATIC RESOURCES
                vd: 
                    + CSS
                    + Javascript
                    + Images 
                    + other files

   **NOTE: the STATIC RESOURCES could be sent through Ajax 
        -> it's not actually need to be done in this step 
        -> it can be done as the 7th step 

    6. Browser: DISPLAY the Receive information 

#### NOTE: 
    WEB SERVER is a SOFTWARE that runs on SERVERs (hardware)
        vd: Nginx, Apache,... are WEB SERVERS  
    WEB APPLICATION runs on WEB SERVER 
    
#### Co che hoat dong 
    + Web Server:  
        -> xu ly request tu Client/Browser through HTTP 
        -> send response to client through HTTP
        -> use to SERVE WEB APPLICATION

        Requirements to work well:
            need a large storage
            high internet speed 
            works at all time, high performance 
        -> some webservers that can do that:             
            vd: Apache, Nginx

    + Database:  
        CSDL allow users to: 
            + STORE 
            + QUERY
            + UPDATE
            Data
        Categories: 
            + Simple: text, xml, json, ... 
            + SQL: SQL Lite, SQLServer, MySQL... 
            + No-SQL: MongoDB, Redis,... 

#### Mot so Fullstack trien khai ung dung 
    + LAMP (Linux Apache MySQL PHP) Stack 
    + LEMP (Linux Nginx MySQL PHP) Stack 
    + MERN (MongoDB Express React Nodejs) Stack 
        NOTE: 
            Express <-> Mongoose <-> MongoDB 

