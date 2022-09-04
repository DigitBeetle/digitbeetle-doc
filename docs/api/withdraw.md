# 提现
URL: `/api/common/withdraw`  
Method: `POST`

> 参数   

| 参数名            | 类型         | 是否必须   | 描述                                |
| ------------     | ----------- | --------- | ---------------------------------- |
| merchant_id      | string      | YES       | 商户ID                              |
| order_id         | string      | YES       | 订单ID （Digit Beetle 订单）         |
| amount           | number      | YES        | 数量                                |
| coin_name        | string      | YES        | 数字币币种 (USDT.ERC20/USDT.TRC20)   |
| to_address       | string      | YES        | 提现目标地址                            |

> Request

```json
{
    "merchant_id": "FENGLOU",
    "order_id": "B93FCBC849D442DA901548AE6F0EA890",
    "amount": 50,
    "coin_name": "USDT.TRC20",
    "to_address": "TKf3Rqc7f3fd2U7CP4xVbrDmaqYzsKPYR5"
}
```

> Response   

```json
{
    "code": 200,
    "message": "Success"
}
```