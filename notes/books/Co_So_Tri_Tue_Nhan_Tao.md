# CO SO TRI TUE NHAN TAO
notes from books: Co so tri tue nhan tao (KHTN), tg: LE HOAI BAC, TO HOAI VIET 

## NOI DUNG, NHUNG VAN DE CO BAN CUA HE THONG THONG MINH, 3 PHAN:     
    + 1. PHUONG PHAP TIM KIEM HIEU QUA 
    + 2. BIEU DIEN TRI THUC va SUY DIEN 
    + 3. HOC MAY 

## PHAN 1: GIAI QUYET BAI TOAN TREN MAY TINH = PHUONG PHAP TIM KIEM

## CHUONG 1: CAC CHIEN LUOC TIM KIEM KHONG CO THONG TIN (UNINFORMED SEARCH)
    DIEU KIEN TIEN QUYET de GIAI QUYET mot BAI TOAN 
    -> phai BIEU DIEN duoc BAI TOAN do. 
    -> Chuong 1: Thuat toan tim kiem MU 
        (KHONG co them bat ki THONG TIN nao, ngoai DIEU KIEN BAI TOAN)

### 1. BIEU DIEN BAI TOAN TIM KIEM 
    Mot bai toan gom: 
        + YEU CAU/VAN DE
        + LOI GIAI
    -> PP TIM KIEM = TIM ra LOI GIAI trong KHONG GIAN TIM KIEM (search space)

    1. BIEU DIEN mot BAI TOAN TIM KIEM, bao gom 5 THANH PHAN: (1)
        + Khong gian trang thai: 
            -> TAT CA TRANG THAI CO THE CO cua bai toan 

        + Trang thai BAN DAU: 
            -> Noi bat dau tim kiem 

        + HAM trang thai con: 
            -> GENERATE next state from state X 
            -> Khong gian trang thai = Trang thai ban dau + Ham trang thai con 

        + a SET of trang thai DICH/ket thuc: 
            -> Thuoc khong gian trang thai 
            -> Tuy vao bai toan -> 1 hoac n trang thai dich khac nhau 

            vd:  GOAL STATE could be: 
                + SPECIFIC CONCRETE STATE 
                    vd: bai toan nguoi du lich 
                    -> diem ket thuc la diem can den vd: diem A -> F

                + describe through CONSTRAINTS/CONDITIONS 
                    vd: bai toan co vua  
                    -> trang thai "chieu tuong" = trang thai doi phuong khong the ngan can viec quan vua bi tan cong
    
        + HAM CHI PHI duong di: 
            -> Tinh CHI PHI LOI GIAI cua bai toan

    Cach bieu dien nay (1) -
        > we can CONVERT the problem:
            + from: tim LOI GIAI
            + to: tim DUONG DI: 
                + from: trang thai ban dau 
                + to: trang thai dich 
    **2. Do thi 
        De GIAI QUYET bai toan tim kiem: 
            -> **XAC DINH KHONG GIAN TRANG THAI phu hop
            + Dua vao: 
                + Trang thai ban dau
                + Ham trang thai con 
                -> suy ra KHONG GIAN TRANG THAI cua bai toan tim kiem 

        + KHONG GIAN TRANG THAI: 
            ->  a SET of trang thai, CO THE DEN duoc tu TRANG THAI BAN DAU 
            *Bieu dien: do thi (do thi khong gian trang thai, do thi trang thai)
        + DO THI:  
            a SET of VERTICES duoc NOI voi nhau boi cac CUNG 
            Cung noi co the: 
                + co huong (directional) 
                + khong co huong (non-directional)
                + co trong so  (weighted)
                + khong co trong so (non-weighted)
                
        VERTICIE: corresponse to STATE
        CUNG NOI: corresponse to ACTION/TRANSFORMATION: 
            + from: one state 
            + to: another state 

    **3. Trang thai
        TRANG THAI trong bai toan tim kiem:  
            -> REPRESENTATION of a STEP in the PROCESS of solving the problem 
            -> BAO GOM - THONG TIN VE THE GIOI trong bai toan tim kiem 
            vd: 
                + Bai toan 8 puzzles: 
                    THE GIOI cua bai toan:
                        -> MOT BAI CO, bao gom: 
                            + kich thuoc: 3x3 
                            + 8 quan co

                    -> **Trang thai(THONG TIN ve THE GIOI): mot cach sap xep 8 quan co tren ban co 3x3

                + Bai toan tim duong: 
                    THE GIOI cua bai toan:
                        -> Mot thanh pho, bao gom: 
                            + Nhieu diem tren ban do
                            + Co duong noi tu diem nay den diem khac

                    -> **Trang thai(THONG TIN ve THE GIOI): 
                        (Diem hien tai dang dung, cac duong co the di tu diem do) ?? maybe
                    

    **4. Ham TRANG THAI CON 
            Ham mo ta: 
                -> ACTION/TRANSFORMATION that CAN BE DONE on a particular STATE 

            -> Give a particular STATE X
            ham Con(x):
                + return: a set of pairs of { (action1, trang thai con1), (action2, trang thai con2),... }
                    + trong do: 
                        + action: ONE of the VALID ACTIONS on STATE X 
                        + trang thai con: RESULTED STATE from action(x) 
            vd: 
                State: From(Ha Giang)
                Ham Trang thai: Con(From(Ha Giang)) 
                    return: a set of pairs = { ( Di(Tuyen Quang), From(Tuyen Quang)),...}

    **5. CHI PHI duong di 
        ... 

## CHUONG 2:      
    ... 

## CHUONG 3:      
    ... 
