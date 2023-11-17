# ZALOPAY API 
notes from this site: https://docs.zalopay.vn/v2/general/overview.html
https://docs.zalopay.vn/v1/start/#A

## Cong thanh toan Zalopay: 
ho tro thanh toan truc tuyen 
giua: 
    + nguoi ban 
    + khach hang 

Cong thanh toan: trung gian giua:
    + nguoi ban 
    + zalopay 
    -> xu ly thanh toan: bao gom:
        + the ATM 
        + the tin dung 
        + vi ZaloPay @This one ??  
        + VietQR


## Prerequisites: 
    Tham so quan trong: 
        api_id, mac_key 
    Hieu cac hoat dong cua API: 
        + CreateOrder 
        + QueryOrder 
        + GetListBanks

    Khai niem: 
        + callback: 
            -> ... 
        + redirect:  
            -> ... 
        + truyen du lieu an toan: 
            -> ...
            
## Cach hoat dong: 
    // Steps: 
    1. Nguoi mua chon phuong thuc thanh toan -> GUI REQUEST thanh toan den Server
    2. Server tao 1 LENH THANH TOAN = CreateOrderAPI -> Backend Gui request den Cong thanh toan 
        -> return URL den trang cong thanh toan 
    3. Front-end REDIRECT den trang cong thanh toan 
    4. Nguoi mua hoan tat thanh toan
        -> Su dung payment method duoc show len 
    5. Front-end REDIRECT ve giao dien cu 
    6. Backend nhan duoc KET QUA GIAO DICH tu callback 
    7. Backend gui thong bao xac nhan giao dich den Front-end

## Tich hop: 
    1. Tao 1 don dat hang 
        with these information: (detail code in this link: https://beta-docs.zalopay.vn/vi/docs/guides/payment-acceptance/checkout/intro/#step-2)

            const order = {
                app_id: configZLP.app_id,
                app_trans_id: appTransID,
                app_user: "user123",
                app_time: Date.now(), // miliseconds
                item: JSON.stringify(items),
                embed_data: JSON.stringify(embed_data),
                amount: 50000,
                description: `Payment for the order #${transID}`,
                bank_code: bankCode,
                callback_url: configZLP.callback_url
            };

            const data = [configZLP.app_id, order.app_trans_id, order.app_user, order.amount, order.app_time, order.embed_data, order.item].join("|");
            order.mac = CryptoJS.HmacSHA256(data, configZLP.key1).toString();

            Notes: 
                Sử dụng đúng bank_code để hiển thị tùy chọn Cổng thanh toán ZaloPay mà bạn muốn.

## API 
    Tao don hang: 
    Hoan tien: 