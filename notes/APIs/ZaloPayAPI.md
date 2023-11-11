# ZALOPAY API 
notes from this site: https://docs.zalopay.vn/v2/general/overview.html
https://docs.zalopay.vn/v1/start/#A

Tao don hang: 
    createOrder(app_trans_id, app_time, embed_data, mac, item, app_user, amount, bank_code, ...) 
        -> return orderInfo(
            order_url, return_code, return_message, zp_trans_token
            )

    Content-Type:
        application/x-www-form-urlencoded
        application/json
        application/xml

    test api: POST https://sb-openapi.zalopay.vn/v2/create
    real api: POST https://openapi.zalopay.vn/v2/create

    Tham so bat buoc: 
        app_id 