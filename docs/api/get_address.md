# 获取地址(用于下分到交易所)
URL: `/external/getRechargeAddress`  
Method: `POST`

> 参数   

| 参数名        | 类型         | 是否必须   | 描述                                | 例子                 |
| ------------ | ----------- | --------- | ---------------------------------- | -------------------- |
| loginName    | string      | YES       | 交易所账号                           |  DK10177             |
| currency     | string      | YES       | 币种                                | USDT/USDC/ETH等      |
| protocol     | string      | NO       | 协议，currency为USDT/USDC时不传协议会返回交易所当前所有协议的地址 | ERC20/TRC20/BEP20/POLYGON         |

> Request   

```json
{
    "loginNanme": "DK10177",
    "currency": "USDT",
    "protocol": "ERC20"
}
```

> Response   

```json
{
    "head": {
        "code": "0000",
        "message": "成功",
        "fieldErrs": null
    },
    "body": [
        {
            "loginName": "DK10660",
            "currency": "USDT",
            "protocol": "ERC20",
            "address": "0xb53615767Ee61E1628bCD87Ff95d8112c4e18Bb4",
        },{
            "loginName": "DK10660",
            "currency": "USDT",
            "protocol": "TRC20",
            "address": "TKo28g9ZzBfyFV2bRU3cP32zg1GvALgxmB",
        }
    ]
}
```