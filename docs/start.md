# 准备1
### 接口调用准备
> 接口请求方法：POST  
> 接口参数类型：JSON  
> 接口签名算法：hmac-MD5  
> 接口Header必填参数，如下：  

| key          | value       | description                          |
| ------------ | ----------- | ------------------------------------ |
| Content-Type | application | 指定请求参数格式JSON                    |
| sign         |             | 参数签名                              |

### 获取ApiKey
联系Digit Beetle工作人员，申请并注册商户号，获取ApiKey
> 获取ApiKey  

![IMAGE](https://github.com/CoinMeta/digitbeetle-doc/blob/main/docs/_media/ex.png?raw=true)

### 参数签名
> Step 1.    

`所有有值参数都要参与签名，将值非空的参数按照参数名ASCII码字典序以键值对(key-value)格式用&连接排列组成字符串，例：key1=value1&key2=value2&key3=value3`  
> Step 2.    

`使用生成的RSA私钥，对Step1中生成的字符串进行签名(签名算法为hmac-MD5),得到的签名字符串放进Header中的sign中`   

> *注意事项：*  
> *以参数名的ASCII码字典序排序，相关语言都有对应的函数可以直接使用，如：PHP的ksort, Java的Collection.sort*   
> *参数名区分要区分大小写，大写的A ASCII码是65，小写的是97*   
> *排序只与参数名有关，与参数值无关*    
> *参数值为空则不参与签名*
