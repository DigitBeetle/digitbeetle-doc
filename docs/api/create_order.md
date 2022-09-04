# 创建支付订单
URL: `/api/common/create-order`  
Method: `POST`

> 参数   

| 参数名            | 类型         | 是否必须   | 描述                                |
| ------------     | ----------- | --------- | ---------------------------------- |
| merchant_id      | string      | YES       | 商户ID                              |
| ref_user_id      | string      | YES       | 用户ID（商户内部）                    |
| ref_order_id     | string      | YES       | 订单ID（商户内部）                    |
| amount           | number      | NO        | 数量                                |
| coin_name        | string      | NO        | 数字币币种 (USDT.ERC20/USDT.TRC20)   |
| price_amount     | number      | NO        | 法币金额                            |
| price_currency   | string      | NO        | 法币币种 (CNY/USD/PHP/JPY)          |
| receive_currency | string      | NO        | 提款币种 (USDT.ERC20/USDT.TRC20)    |

> Request (数字币充值) 

```json
{
    "merchant_id": "FENGLOU",
    "ref_user_id": "13800138000",
    "ref_order_id": "20220725103012560001",
    "amount": 50,
    "coin_name": "USDT.TRC20"
}
```

> Request (法币计价充值) 

```json
{
    "merchant_id": "FENGLOU",
    "ref_user_id": "13800138000",
    "ref_order_id": "20220725103012560001",
    "price_amount": 50,
    "price_currency": "CNY"
}
```

> Response   

```json
# 使用payment_url跳转支付
{
    "code": 200,
    "message": "Success",
    "data": {
        "amount": 22,
        "coin_name": "USDT.TRC20",
        "create_time": "2022-07-26 16:33:23",
        "is_refundable": 0,
        "order_id": "B93FCBC849D442DA901548AE6F0EA890",
        "overpaid_amount": 0,
        "payment_url": "https://pay.digitbeetle.com/invoice/B93FCBC849D442DA901548AE6F0EA890",
        "price_amount": 0,
        "price_currency": null,
        "receive_amount": 0,
        "receive_currency": "",
        "underpaid_amount": 0
    }
}
```