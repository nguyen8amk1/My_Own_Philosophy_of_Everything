# QUY HOACH TUYEN TINH, ROI RAC
notes from books and videos of Bui The Tam: 
    Bai toan quy hoach tuyen tinh 
    Bai toan quy hoach roi rac 

Thuat toan can:
    + xay dung co so ly thuyet 
    + chung minh tinh:  
        + huu han
        + hoi tu
    + phai lap trinh duoc

## Bai toan toi uu TONG QUAT: 
    -> Cuc dai hoa (cuc tieu hoa) ham 
    f(x) -> max(min) (1.1)
        -> f(x): ham muc tieu 

    voi cac dieu kien: 
        gi(x) (<=, = , >=) bi, i = 1...m -> gi(x) cac ham RANG BUOC 
        x thuoc X con cua R^n

    MIEN RANG BUOC (mien chap nhan duoc): 
        D = { x thuoc X | gi(x) (<=, = , >=) bi, i = 1...m }

    Note: x la 1 VECTOR co size = n 
    x = (x1, x2, x3,... xn) thuoc D = mot PHUONG AN CHAP NHAN DUOC 

    Mot phuong an x* thuoc D, dat cuc dai (cuc tieu) cua ham muc tieu 

    f(x*) >= f(x), voi moi x thuoc D (max)
    f(x*) <= f(x), voi moi x thuoc D (min)

    ->    x* = phuong an toi uu 
        f(x*) gia tri toi uu 

## Phan loai bai toan: 

    cac TINH CHAT cua cac THANH PHAN cua bai toan 
        + ham muc tieu 
        + ham rang buoc 
        + bien so 
        + he so 
        + dieu kien: 
            + can cua cuc tri 
            + du cua cuc tri 
            + TON TAI LOI GIAI chap nhan duoc 
        ... 

        -> phan loai bai toan 

    QUY HOACH = BAI TOAN TOI UU 

    phan loai: 
        quy hoach tuyen tinh: 
            Ham muc tieu f(x) 
            Ham rang buoc gi(x), i = 1....m  
            -> la tuyen tinh 
            tap X la mot TAP LOI DA DIEN 

            TRUONG HOP RIENG quan trong: bai toan van tai 

        quy hoach dong: 
            doi tuong xet: 
               general: cac QUA TRINH co NHIEU GIAI DOAN 
               specific: cac QUA TRINH phat trien theo THOI GIAN 

        quy hoach roi rac: 
            mien rang buoc D la tap roi rac 
            truong hop rieng: 
                + quy hoach nguyen
                    -> cac BIEN chi nhan GIA TRI NGUYEN 
                    truong hop rieng: 
                        + quy hoach bien Boole
                            -> cac BIEN chi nhan GIA TRI 0, 1 

        quy hoach tham so: 
        quy hoach loi: 
        quy hoach lom: 
        quy hoach da muc tieu: 

## MO HINH HOA toan hoc cho 1 VAN DE THUC TE 
    4 buoc: 
    1. Xay dung MO HINH DINH TINH cho van de thuc te: 
        -> XAC DINH cac YEU TO:
            + co Y NGHIA QUAN TRONG nhat 
            + xac lap cac QUY LUAT ma chung phai tuan theo 
        -> Phat bieu mo hinh bang: 
            + loi 
            + bieu do
            + dieu kien
            + muc tieu 

    2. Xay dung MO HINH cho van de dang xet 
        -> DIEN TA lai duoi dang NGON NGU TOAN HOC cho MO HINH DINH TINH
        Chon cac BIEN SO DAC TRUNG cho TRANG THAI cua he thong 
        Mo hinh toan hoc: 
            thiet lap:
                MOI LIEN HE giua:
                    + cac BIEN SO 
                    + cac HE SO DIEU KHIEN HIEN TUONG 
            
        Quan trong: 
            + Xac dinh HAM MUC TIEU 
                -> Mot DAC TRUNG BANG SO ma GIA TRI CANG LON/NHO cua no 
                    tuong ung voi HIEU QUA CANG TOT
                    giai quyet van de ma nguoi nhan loi giai mong muon 
            + Rang buoc toan hoc: 
                -> cac dieu kien/rang buoc ma cac bien so phai tuan theo 
                    DIEN TA bang cac: 
                        + phuong trinh 
                        + bat phuong trinh

    3. KHAO SAT, GIAI QUYET BAI TOAN hinh thanh trong BUOC 2 (DUNG CONG CU TOAN HOC): 
        Can cu vao mo hinh o buoc 2
        -> chon, xay dung PHUONG PHAP GIAI cho phu hop 
        -> CU THE HOA phuong phap = THUAT TOAN tren may tinh 

    4. PHAN TICH, KIEM DINH lai KET QUA thu duoc trong buoc 3
        -> Xac dinh MUC DO PHU HOP cua mo hinh, KET QUA TINH TOAN
            voi van de thuc te
            ..... 
## NOTES: 
    Nodes have their values:  
        -> Can be represent through Array 
        -> Represent the VALUE of a CERTAIN PROPERTY of a node 
            ai, bj

    Links also have their values 
        -> Represent the relation (VALUE OF EXECUTING SOME WORK) between 2 nodes
            aij, cij  
        -> Can be represent through Matrices 

    Nodes are their own objects 
    Links are also their own objects 

    -> Mathematical model usually SEPARATE EACH INDIVIDUALS PROPERTIES into their own data structure
        -> For NODE PROPERTIES: Each properties of nodes into it's own array 
        vd: 
        Given:  
            node { 
                int a, 
                int b, 
                int c
            }

            Have n nodes = nodes[n]
                i = 1...n 
                -> value of a in node i 
                    -> nodes[i].a 

            -> Mathemtical modeling -> 
                int as[n]
                int bs[n]
                int cs[n]
                with i = 1...n 

                -> value of a in node i 
                    -> as[i]

        -> For LINKS PROPERTIES: Each properties of links into it's own MATRICE 
        vd: 
            link {
                int from; 
                int to; 

                int a; 
                int b; 
            }

            -> have nxn links = links[n][n]
                i = 1...n 
                j = 1...n 

                -> value of a from node i to node j 
                    -> links[i][j].a 

            -> Mathematical modeling ->  
                int a[n][n]
                int b[n][n]

                -> value of a from node i to node j 
                    -> a[i][j]

## TIPs: 
    thinks of the objects in the problem as: 
        + Nodes
        + Links (some problem will not exist links)
        -> each have their own properties 
        then separate them into array and matrices according to the type (Node, Link)

    Contraints: 
        Checking for resources usage 
        DAU CUA BIEN SO (THINGS THAT NEED TO BE FOUND IN THE OBJECTIVE FUNCTION)
