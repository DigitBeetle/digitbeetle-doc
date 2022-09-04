# 新用户注册
URL: `/external/register`  
Method: `POST`

> 参数   

| 参数名        | 类型         | 是否必须   | 描述                                | 例子                 |
| ------------ | ----------- | --------- | ---------------------------------- | -------------------- |
| netSource    | string      | YES       | 用户来源                            |  A01/A02/A03 等      |
| phone        | string      | YES       | 用户手机号，用Base64编码              | MTMONTU2Nj=          |
| countryCode  | string      | YES       | 手机号国际区号                       | 86/63/886 等         |
| password     | string      | NO        | 用户登录密码MD5                      | e99a18ccb74856a4545 |
| nickName     | string      | NO        | 用户昵称                            | 萨菲罗斯              |
| terminalType | string      | NO        | 用户设备类型                         | ios                 |
| loginName       | string   | NO        | 交易所账号                         | DK10177              |

> Request   

```json
{
    "netSource": "A01",
    "phone": "MTMONTU2Nj=",
    "countryCode": "86",
    "password": "e99a18ccb74856a4545",
    "nickName": "萨菲罗斯",
    "terminalType": "ios"
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
    "body": "DK10177"
}
```