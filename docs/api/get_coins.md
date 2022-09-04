# 获取币种列表
URL: `/api/common/get-coins`  
Method: `POST`

> 参数   

| 参数名        | 类型         | 是否必须   | 描述                                |
| ------------ | ----------- | --------- | ---------------------------------- |
| merchant_id  | string      | YES       | 商户ID                              |
| ref_user_id  | string      | YES       | 用户ID（商户内部）                    |

> Request   

```json
{
    "merchant_id": "FENGLOU",
    "ref_user_id": "13800138000"
}
```

> Response   

```json
{
    "code": 200,
    "message": "Success",
    "data": [
        {
            "coin_symbol": "USDT",
            "icon": "https://static-coinmeta.runfast123.com/imgs/coins/D05B8596E7E0410D9B54A5FF337E30BA.png",
            "merchant_id": "FENGLOU",
            "coin_address": "TY7NUK2JY1Y3dS5kmewPi1JouYUmT1mimg",
            "update_time": "2022-06-03 06:22:36",
            "coin_full_name": "Tether USD",
            "coin_name": "USDT.TRC20",
            "coin_status": 1,
            "id": 15,
            "status": 1
        }
    ]
}
```