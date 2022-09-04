# 充值/支付/提现回调（商户实现订阅）
URL: `${merchant_api_url}/callback`  
Method: `POST`

> 参数   
 
请求头参数： sign (商户验签)

##### deposit-充值

| 参数名            | 类型         | 是否必须    | 描述                                |
| ------------     | ----------- | ---------  | ---------------------------------- |
| method           | string      | YES        | withdraw                           |
| merchant_id      | string      | YES        | 商户ID                              |
| ref_user_id      | string      | YES        | 用户ID（商户内部）                    |
| ref_order_id     | string      | NO         | 订单ID（商户内部）                   |
| order_id         | string      | YES        | 订单ID （Digit Beetle 订单）         |
| to_user          | string      | YES        | 用户ID （Digit Beetle 用户）         |
| to_address       | string      | YES        | 目标地址                            |
| amount           | string      | YES        | 数量                                |
| fee              | string      | NO        | 手续费                              |
| coin_name        | string      | YES        | 数字币币种 (USDT.ERC20/USDT.TRC20)   |
| status           | string      | YES        | 状态 1: INITIAL, 2: PROCESSING, 3: FINISHED, 4: FAILED, 5: CANCELED |

> Request (deposit-充值)

```json
{
    "method": "deposit",
    "merchant_id": "FENGLOU",
    "ref_user_id": "XXXXXXXXX",
    "ref_order_id": "",
    "order_id": "B93FCBC849D442DA901548AE6F0EA890",
    "to_user": "BF7458745",
    "to_address": "TKf3Rqc7f3fd2U7CP4xVbrDmaqYzsKPYR5",
    "amount": "50",
    "fee": "",
    "coin_name": "USDT.TRC20",
    "status": "3"
}
```

##### payment-支付: create-order

| 参数名            | 类型         | 是否必须   | 描述                                |
| ------------     | ----------- | --------- | ---------------------------------- |
| method           | string      | YES       | payment                            |
| merchant_id      | string      | YES       | 商户ID                              |
| ref_user_id      | string      | YES       | 用户ID（商户内部）                    |
| ref_order_id     | string      | YES       | 订单ID（商户内部）                   |
| order_id         | string      | YES       | 订单ID （Digit Beetle 订单）         |
| to_user          | string      | YES       | 用户ID （Digit Beetle 用户）         |
| to_address       | string      | YES       | 目标地址                            |
| amount           | string      | YES       | 数量                               |
| fee              | string      | NO        | 手续费                              |
| coin_name        | string      | YES       | 数字币币种 (USDT.ERC20/USDT.TRC20)  |
| status           | string      | YES       | 状态 1: INITIAL, 2: PROCESSING, 3: FINISHED, 4: FAILED, 5: CANCELED |

> Request (payment-支付: create-order)

```json
{
    "method": "payment",
    "merchant_id": "FENGLOU",
    "ref_user_id": "XXXXXXXXX",
    "ref_order_id": "20220725103012560001",
    "order_id": "B93FCBC849D442DA901548AE6F0EA890",
    "to_user": "BF7458745",
    "to_address": "TKf3Rqc7f3fd2U7CP4xVbrDmaqYzsKPYR5",
    "amount": "50",
    "fee": "",
    "coin_name": "USDT.TRC20",
    "status": "3"
}
```

##### withdraw-提现

| 参数名            | 类型         | 是否必须   | 描述                                |
| ------------     | ----------- | --------- | ---------------------------------- |
| method           | string      | YES       | withdraw                           |
| merchant_id      | string      | YES       | 商户ID                              |
| ref_user_id      | string      | YES       | 用户ID（商户内部）                    |
| ref_order_id     | string      | YES       | 订单ID（商户内部）                   |
| order_id         | string      | YES       | 订单ID （Digit Beetle 订单）         |
| to_user          | string      | NO        | 用户ID （Digit Beetle 用户）         |
| to_address       | string      | YES       | 目标地址                            |
| amount           | string      | YES       | 数量                               |
| fee              | string      | YES       | 手续费                              |
| coin_name        | string      | YES       | 数字币币种 (USDT.ERC20/USDT.TRC20)  |
| status           | string      | YES       | 状态 1: INITIAL, 2: PROCESSING, 3: FINISHED, 4: FAILED, 5: CANCELED |

> Request (withdraw-提现)

```json
{
    "method": "withdraw",
    "merchant_id": "FENGLOU",
    "ref_user_id": "XXXXXXXXX",
    "ref_order_id": "20220725103012560001",
    "order_id": "B93FCBC849D442DA901548AE6F0EA890",
    "to_user": "",
    "to_address": "TKf3Rqc7f3fd2U7CP4xVbrDmaqYzsKPYR5",
    "amount": "50",
    "fee": "1",
    "coin_name": "USDT.TRC20",
    "status": "3"
}
```

> Response   

##### 响应code为200，并且message为"Success"代表成功，并回传商户自己的订单ID

```json
{
    "code": 200,
    "message": "Success",
    "data": {
        "ref_order_id": "20220725103012560001"
    }
}
```