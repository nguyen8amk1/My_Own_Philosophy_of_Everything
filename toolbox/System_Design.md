# VALUABLE SYSTEM DESIGN 

## PAYMENT GATEWAY 
HOW VNPAY PAYMENT GATEWAY WORKS 
The Loop: 
Khach hang -> Website thuong mai -> VNPAY -> Ngan Hang
Ngan Hang -> VNPAY -> Website thuong mai -> Khach hang 

Steps: 
    Client thuc hien thanh toan truc tuyen tren Website 
    Website: 
        1. tao thong tin thanh toan: (duoi dang URL mang thong tin thanh toan) 
        2. Chuyen huong khach hang sang cong thanh toan VNPAY 
    Client nhap thong tin xac minh tai khoan Ngan hang va xac thuc giao dich 
    Giao dich thanh cong tai ngan hang -> VNPAY chuyen huong khach hang den website hien thi cho nguoi dung vnp_ReturnUrl 
    Thong bao ket qua thanh toan cua client thong qua vnp_InpURL 
    