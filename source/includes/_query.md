# 查询列表

## 查询法币币种

### 应用场景

用于在调用BitFS法币币种充值/提币接口时，查询BitFS所支持的法币币种，这样可以实时校验调用接口币种是否支持。 

### 概括

* API名称：查询充值/提币支持的法币币种接口
* 请求方式：HTTP GET
* 请求URL：pay/v1/currencyList

### 请求参数

NULL

### 返回结果

| 变量名 | 必填 | 类型        | 示例值  | 描述                                                      |
| ------ | ---- | ----------- | ------- | --------------------------------------------------------- |
| code   | true | Int         | 0       | 返回状态码：调用成功时返回0                               |
| msg    | true | String(255) | success | 返回信息：当code不为0时返回信息为错误原因 ，例如:请求超时 |

<aside class="notice">以下字段在code=0时有返回</aside>

| 变量名   | 必填 | 类型   | 示例值 | 描述       |
| -------- | ---- | ------ | ------ | ---------- |
| fee_name | true | String | 人民币 | 法币的名称 |
| fee_type | true | String | CNY    | 法币编码值 |



## 查询数字货币币种

### 应用场景

用于在调用BitFS数字货币币种充值/提币接口时，查询BitFS所支持的数字货币币种，这样可以实时校验调用接口币种是否支持。 

### 概括

* API名称：查询充值/提币支持的数字货币币种接口
* 请求方式：HTTP GET
* 请求URL：pay/v1/digiccyList

### 请求参数

NULL

### 返回结果

| 变量名 | 必填 | 类型        | 示例值  | 描述                                                      |
| ------ | ---- | ----------- | ------- | --------------------------------------------------------- |
| code   | true | Int         | 0       | 返回状态码：调用成功时返回0                               |
| msg    | true | String(255) | success | 返回信息：当code不为0时返回信息为错误原因 ，例如:请求超时 |

<aside class="notice">以下字段在code=0时有返回</aside>

| 变量名   | 必填 | 类型   | 示例值 | 描述           |
| -------- | ---- | ------ | ------ | -------------- |
| fee_name | true | String | 比特币 | 数字货币的名称 |
| fee_type | true | String | BTC    | 数字货币编码值 |



## 查询商户账户余额

### 应用场景

商户在BitFS注册成功后可以调用本接口方便的查询自身账户余额，灵活调整自身业务。

### 概括

* API名称：查询商户账号余额接口

* 请求方式：HTTP  POST

* 请求URL：pay/v1/checkacct

### 请求参数

> request:

~~~java
{
    "mch_id":"441649692783284224",
    "nonce_str":"FEC838C0BEA5468A82E2467DA4F70B8C",
    "fee_type":"usdt",
    "appKey":"f09b650179d5e01930d9c7b78c300147&3129384845945498",
    "sign":"F752ABD95162A4A95E7C4A5E33DAEDD9”
}
~~~

| 变量名    | 必填  | 类型   | 示例值                           | 描述                |
| --------- | ----- | ------ | -------------------------------- | ------------------- |
| mch_id    | true  | String | 441649692783284224               | BitFS分配给商户的id |
| nonce_str | true  | String | FEC838C0BEA5468A82E2467DA4F70B8C | 随机字符            |
| fee_type  | true  | String | BTC                              | 币编码              |
| appkey    | true  | String | fc798420836184e33c042de1caa2814a | BitFS分配的appkey   |
| sign      | true  | String | F752ABD95162A4A95E7C4A5E33DAEDD9 | 签名                |
| sign_type | false | String | MD5                              | 签名类型，默认MD5   |

### 返回结果

> response:

~~~java
{
    "code": 0,
    "msg": "請求成功",
    "result": "{
        "mch_id":"441649692783284224",
    	"balance":"1000.56812",
    	"freeze":"1236.9872",
    	"nonce_str":"FEC838C0BEA5468A82E2467DA4F70B8C",
    	"sign":"F752ABD95162A4A95E7C4A5E33DAEDD9"

	}"
}
~~~

| 变量名 | 必填 | 类型        | 示例值  | 描述                                                         |
| ------ | ---- | ----------- | ------- | ------------------------------------------------------------ |
| code   | true | Int         | 0       | 网关返回码：调用成功时返回0                                  |
| msg    | true | String(255) | success | 返回信息：当code不为0时返回信息为错误原因 ，例如 :参数校验错误 |

<aside class="notice">以下字段在code为0时有返回</aside>

| 变量      | 必填 | 类型   | 示例值                           | 描述                     |
| --------- | ---- | ------ | -------------------------------- | ------------------------ |
| mch_id    | true | String | 441649692783284224               | BitFS分配给商户的id      |
| balance   | true | String | 1000.56812                       | 商户当前币种的可用余额   |
| freeze    | true | String | 1236.9872                        | 商户当前币种的冻结的数量 |
| nonce_str | true | String | FEC838C0BEA5468A82E2467DA4F70B8C | BitFS返回的随机字符串    |
| sign      | true | String | F752ABD95162A4A95E7C4A5E33DAEDD9 | BitFS返回的签名          |

### 错误码

| 名称                   | 描述                         | 原因                         | 解决方案                                   |
| ---------------------- | ---------------------------- | ---------------------------- | ------------------------------------------ |
| APPKEY_MCHID_NOT_MATCH | 商户machId与商户appkey不匹配 | 商户machId与商户appkey不匹配 | 请确认appid和mch_id是否匹配                |
| SIGNERROR              | 签名错误                     | 参数签名结果不正确           | 请检查签名参数和方法是否都符合签名算法要求 |
| LACK_PARAMS            | 缺少参数                     | 缺少必要的请求参数           | 请检查参数是否齐全                         |
| SYSTEMERROR            | 系统错误                     | 系统超时                     | 系统异常，请用相同参数重新调用             |
| COIN_NOT_EXIST         | 币种不支持                   | 请求的币种不支持             | 请参考币种列表上传正确的币种               |

## 查询订单

### 应用场景

该接口提供所有BitFS支付订单的查询，商户可以通过查询订单接口主动查询订单状态，完成下一步的业务逻辑。

**需要调用查询接口的情况**

- 当商户后台、网络、服务器等出现异常，商户系统最终未接收到支付通知；
- 调用支付接口后，返回系统错误或未知交易状态情况；

### 概述

- API名称：代理商订单查询接口

- 请求方式：HTTP POST

- 请求URL：pay/v1/queryorder

### 请求参数

> request:

~~~java
{
    "mch_id":"441649692783284224",
    "out_trade_no":"7faf7e60a92d4afa963b83933a949ecc",
    "nonce_str":"FEC838C0BEA5468A82E2467DA4F70B8C",
    "appKey":"a58b139c85adbccf3a4b3a8e83a2bfba",
    "sign":"FB87C3106C43DF67513ABDFE8029A096"
}
~~~

| 变量         | 必填  | 类型   | 示例值                           | 描述                                         |
| ------------ | ----- | ------ | -------------------------------- | -------------------------------------------- |
| mch_id       | true  | String | 441649692783284224               | BitFS分配的商户                              |
| out_trade_no | true  | String | 7faf7e60a92d4afa963b83933a949ecc | 商户系统内部的订单号：32个字符内、可包含字母 |
| nonce_str    | true  | String | FEC838C0BEA5468A82E2467DA4F70B8C | 随机字符串                                   |
| sign_type    | false | String | MD5                              | 签名类型：默认为MD5                          |
| appKey       | true  | String | a58b139c85adbccf3a4b3a8e83a2bfba | 商户的appkey                                 |
| sign         | true  | String | FB87C3106C43DF67513ABDFE8029A096 | 签名                                         |

### 返回结果

> response:

~~~java
{
    "code": 0,
    "msg": "請求成功",
    "result": "{
        "mch_id":"441649692783284224",
    	"out_trade_no":"7faf7e60a92d4afa963b83933a949ecc",
    	"total_amount":"14.14",
    	"transaction_id":"44240523622d4b2ca836176cd88085d3",
    	"trade_type":"DEPOSIT",
    	"fee_type":"CNY",
    	"attach":"广州分店充值",
    	"trade_state":"100",
    	"tick_price":"7.00",
    	"order_fee":"2.02",
    	"trade_state_desc":"交易取消",
    	"nonce_str":"FEC838C0BEA5468A82E2467DA4F70B8C",
    	"sign":"F752ABD95162A4A95E7C4A5E33DAEDD9"
	}"
}
~~~

| 变量名 | 必填 | 类型        | 示例值  | 描述                                                         |
| ------ | ---- | ----------- | ------- | ------------------------------------------------------------ |
| code   | true | Int         | 0       | 网关返回码：调用成功时返回0                                  |
| msg    | true | String(255) | success | 返回信息：当code不为0时返回信息为错误原因 ，例如参数校验错误 |

<aside class="notice">以下字段在code为0时有返回</aside>

| 变量             | 必填  | 类型   | 示例值                           | 描述                                                         |
| ---------------- | ----- | ------ | -------------------------------- | ------------------------------------------------------------ |
| mch_id           | true  | String | 441649692783284224               | BitFS分配的商户                                              |
| customer_id      | false | String | 442314630598103040               | 扫码交易用户标识，当用户扫码获取订单时该字段有返回。         |
| out_trade_no     | true  | String | 7faf7e60a92d4afa963b83933a949ecc | 商户系统内部的订单号,32个字符内、可包含字母。                |
| nonce_str        | true  | String | FEC838C0BEA5468A82E2467DA4F70B8C | 随机字符串                                                   |
| total_amount     | true  | String | 14.14                            | 商户请求交易的金额：当fee_type为法币时单位为元；当fee_type为数字货币时单位为 1个 |
| transaction_id   | true  | String | 44240523622d4b2ca836176cd88085d3 | BitFS生成的订单号                                            |
| trade_type       | true  | String | WITHDRAW                         | 交易类型：充币:DEPOSIT;  提币:WITHDRAW                       |
| fee_type         | true  | String | CNY                              | 发起请求的交易币种：分为法币和数字货币，[详见法币列表](#d6a9971a56)。 |
| tick_price       | true  | String | 7.00                             | 发起请求时的BitFS行情价。                                    |
| order_fee        | true  | String | 2.02                             | 实际交易的数字货币（USDT）数量。                             |
| attach           | false | String | ”广州分店充值“                   | 商家的附加信息                                               |
| trade_state      | true  | String | 100                              | 交易状态：100 交易成功 ;200 交易失败;300 交易取消            |
| trade_state_desc | true  | String | 交易取消                         | 对交易状态的描述。                                           |
| sign             | true  | String | F752ABD95162A4A95E7C4A5E33DAEDD9 | 签名。                                                       |

### 错误码

| 名称                   | 描述                         | 原因                         | 解决方案                                                     |
| ---------------------- | ---------------------------- | ---------------------------- | ------------------------------------------------------------ |
| APPKEY_MCHID_NOT_MATCH | 商户machId与商户appkey不匹配 | 商户machId与商户appkey不匹配 | 请确认appid和mch_id是否匹配                                  |
| SIGNERROR              | 签名错误                     | 参数签名结果不正确           | 请检查签名参数和方法是否都符合签名算法要求                   |
| LACK_PARAMS            | 缺少参数                     | 缺少必要的请求参数           | 请检查参数是否齐全                                           |
| SYSTEMERROR            | 系统错误                     | 系统超时                     | 系统异常，请用相同参数重新调用                               |
| ORDERNOTEXIST          | 订单号不存在                 | 查询系统中不存在此交易订单号 | 该API只能查提交交易返回成功的商户订单，请商户检查需要查询的商户订单号是否正确 |
