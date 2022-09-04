# 检测用户是否注册

URL: `/external/phoneCheck`  
Method: `POST`

> 参数   

| 参数名        | 类型         | 是否必须   | 描述                                | 例子                 |
| ------------ | ----------- | --------- | ---------------------------------- | -------------------- |
| phone        | string      | YES       | 用户手机号，用Base64编码              | MTMONTU2Nj=          |
| countryCode  | string      | YES       | 手机号国际区号                       | 86/63/886 等         |

> Request   

```json
{
    "phone": "MTMONTU2Nj=",
    "countryCode": "86"
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
    "body": {
        "isRegister": true,    // true: 该手机号已注册, false: 手机号未注册
        "loginName": "DK32899"
    }
}
```