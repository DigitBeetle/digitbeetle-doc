# 查询用户资产（自动注册）
URL: `/api/common/query-assets`  
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
            "id": 265,
            "balance": 0,
            "icon": "https://static-coinmeta.runfast123.com/imgs/coins/C701FCCFB1ED4161B1E8E826B27E7D49.png",
            "address": "0x5F44bF704887b62ef4DcB24f3d1cfDb6E42cA19b",
            "member_id": 1122,
            "coin_name": "USDC.ERC20",
            "coin_full_name": "USD Coin",
            "coin_symbol": "USDC",
            "coin_status": 0
        },
        {
            "id": 266,
            "balance": 0,
            "icon": "https://static-coinmeta.runfast123.com/imgs/coins/D05B8596E7E0410D9B54A5FF337E30BA.png",
            "address": "TY7NUK2JY1Y3dS5kmewPi1JouYUmT1mimg",
            "member_id": 1122,
            "coin_name": "USDT.TRC20",
            "coin_full_name": "Tether USD",
            "coin_symbol": "USDT",
            "coin_status": 1
        }
    ]
}
```