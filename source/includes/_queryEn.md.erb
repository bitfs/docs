# Query List

 

## Query Fiat Currency

### Application Scenario

It is used to query the fiat currency supported by BitFS when calling the BitFS fiat currency recharge/withdraw interface, so that it can verify whether the calling interface currency is supported in real time.

### Generalize

* Name：Query the fiat currency interface supported by deposit / withdraw
* Request Method：HTTP GET
* Request URL：pay/v1/currencyList

### Request Parameters

NULL

### Response Content

| Parameter | Required | Type        | Example | Description                                                  |
| --------- | -------- | ----------- | ------- | ------------------------------------------------------------ |
| code      | true     | Int         | 0       | Return status code: return 0 when the call is successful     |
| msg       | true     | String(255) | success | Return information: when the code is not 0, the return information is the cause of the error, for example: request timeout |

<aside class="notice">The following Field Name is returned when code = 0</aside>

| Parameter | Required | Type   | Example | Description                   |
| --------- | -------- | ------ | ------- | ----------------------------- |
| fee_name  | true     | String | CNY     | The name of the fiat currency |
| fee_type  | true     | String | CNY     | Fiat code value               |



## Query Digital Currency 

### Application Scenario

It is used to query the digital currency currencies supported by BitFS when calling the BitFS digital currency currency recharge/withdrawal interface, so that it can verify whether the calling interface currency is supported in real time.

### Generalize

* Name：Query digital currency currency interface supported by deposit / withdraw
* Request Method：HTTP GET
* Request URL：pay/v1/digiccyList

### Request Parameters

NULL

### Response Content

| Parameter | Required | Type        | Example | Description                                                  |
| --------- | -------- | ----------- | ------- | ------------------------------------------------------------ |
| code      | true     | Int         | 0       | Return status code: return 0 when the call is successful     |
| msg       | true     | String(255) | success | Return information: when the code is not 0, the return information is the cause of the error, for example: request timeout |

<aside class="notice">The following Field Name is returned when code = 0</aside>

| Parameter | Required | Type   | Example | Description                 |
| --------- | -------- | ------ | ------- | --------------------------- |
| fee_name  | true     | String | BTC     | Digital currency name       |
| fee_type  | true     | String | BTC     | Digital currency code value |



## Query Merchant Account Balance

### Application Scenario

Merchants can call this interface to query their account balances conveniently after BitFS registration is successful, and adjust their own business flexibly.

### Generalize

* Name：Query merchant balance interface

* Request Method：HTTP  POST

* Request URL：pay/v1/checkacct

### Request Parameters

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

| Parameter | Required | Type   | Example                          | Description                               |
| --------- | -------- | ------ | -------------------------------- | ----------------------------------------- |
| mch_id    | true     | String | 441649692783284224               | The id assigned to the merchant by BitFS. |
| nonce_str | true     | String | FEC838C0BEA5468A82E2467DA4F70B8C | Random string.                            |
| fee_type  | true     | String | BTC                              | Coin Code.                                |
| appkey    | true     | String | fc798420836184e33c042de1caa2814a | Appkey assigned by BitFs.                 |
| sign      | true     | String | F752ABD95162A4A95E7C4A5E33DAEDD9 | Sign.                                     |
| sign_type | false    | String | MD5                              | Signature Type，Default MD5.              |

### Response Content

> response:

~~~java
{
    "code": 0,
    "msg": "success",
    "result": "{
        "mch_id":"441649692783284224",
    	"balance":"1000.56812",
    	"freeze":"1236.9872",
    	"nonce_str":"FEC838C0BEA5468A82E2467DA4F70B8C",
    	"sign":"F752ABD95162A4A95E7C4A5E33DAEDD9"

	}"
}
~~~

| Parameter | Required | Type        | Example | Description                                                  |
| --------- | -------- | ----------- | ------- | ------------------------------------------------------------ |
| code      | true     | Int         | 0       | Gateway return code: return 0 when the call is successful.   |
| msg       | true     | String(255) | success | Return information: when the code is not 0, the return information is the cause of the error, for example: parameter verification error. |

<aside class="notice">The following Field Name is returned when the code is 0</aside>

| Parameter | Required | Type   | Example                          | Description                                        |
| --------- | -------- | ------ | -------------------------------- | -------------------------------------------------- |
| mch_id    | true     | String | 441649692783284224               | The id assigned to the merchant by BitFS.          |
| balance   | true     | String | 1000.56812                       | Available balance of merchant's current currency.  |
| freeze    | true     | String | 1236.9872                        | The number of merchant's current currency freezes. |
| nonce_str | true     | String | FEC838C0BEA5468A82E2467DA4F70B8C | Random string returned by BitFS.                   |
| sign      | true     | String | F752ABD95162A4A95E7C4A5E33DAEDD9 | Sign returned by BitFS.                            |

### Error Code

| Name                   | Description                           | Reason                                  | Solution                                                     |
| ---------------------- | ------------------------------------- | --------------------------------------- | ------------------------------------------------------------ |
| APPKEY_MCHID_NOT_MATCH | machId does not match Merchant AppKey | machId does not match Merchant AppKey   | Please confirm that appid and mch_id match.                  |
| SIGNERROR              | Sign error                            | Parameter Sign result is incorrect      | Please check whether Sign parameters and methods meet the requirements of Sign algorithm. |
| LACK_PARAMS            | Missing parameters                    | Missing required request parameters     | Please check if the parameters are complete.                 |
| SYSTEMERROR            | System error                          | System timeout                          | The system is abnormal, please call again with the same parameters. |
| COIN_NOT_EXIST         | Currency not supported                | The requested currency is not supported | Please refer to the currency list to upload the correct currency. |

## Query Order

### Application Scenario

This interface provides query of all BitFS payment orders. Merchants can actively query the order status through the query order interface to complete the next business logic.

**Need to call the query interface**

- When the merchant background, network, server, etc. are abnormal, the merchant system does not receive the payment notification in the end;
- After calling the payment interface, return System error or unknown transaction status;

### Generalize

- Name：Query merchant order interface

- Request Method：HTTP POST

- Request URL：pay/v1/queryorder

### Request Parameters

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

| Field Name            | Parameter    | Required | Type   | Example                          | Description                                                  |
| --------------------- | ------------ | -------- | ------ | -------------------------------- | ------------------------------------------------------------ |
| Merchant Id           | mch_id       | true     | String | 441649692783284224               | Merchants allocated by BitFs.                                |
| Merchant Order Number | out_trade_no | true     | String | 7faf7e60a92d4afa963b83933a949ecc | Order number within the merchant system: within 32 characters, may contain letters. |
| Random string         | nonce_str    | true     | String | FEC838C0BEA5468A82E2467DA4F70B8C | Random string.                                               |
| Signature Type        | sign_type    | false    | String | MD5                              | Signature type: MD5 by default.                              |
| Appkey                | appKey       | true     | String | a58b139c85adbccf3a4b3a8e83a2bfba | Merchant's appkey.                                           |
| Sign                  | sign         | true     | String | FB87C3106C43DF67513ABDFE8029A096 | Sign.                                                        |

### Response Content

> response:

~~~java
{
    "code": 0,
    "msg": "SUCCESS",
    "result": "{
        "mch_id":"441649692783284224",
    	"out_trade_no":"7faf7e60a92d4afa963b83933a949ecc",
    	"total_amount":"14.14",
    	"transaction_id":"44240523622d4b2ca836176cd88085d3",
    	"trade_type":"DEPOSIT",
    	"fee_type":"CNY",
    	"attach":"Recharge of Guangzhou Branch",
    	"trade_state":"100",
    	"tick_price":"7.00",
    	"order_fee":"2.02",
    	"trade_state_desc":"Cancel Transaction",
    	"nonce_str":"FEC838C0BEA5468A82E2467DA4F70B8C",
    	"sign":"F752ABD95162A4A95E7C4A5E33DAEDD9"
	}"
}
~~~

| Parameter | Required | Type        | Example | Description                                                  |
| --------- | -------- | ----------- | ------- | ------------------------------------------------------------ |
| code      | true     | Int         | 0       | Gateway return code: return 0 when the call is successful.   |
| msg       | true     | String(255) | success | Return information: when the code is not 0, the return information is the cause of the error, for example, parameter verification error. |

<aside class="notice">The following Field Name is returned when the code is 0</aside>

| Parameter        | Required | Type   | Example                          | Description                                                  |
| ---------------- | -------- | ------ | -------------------------------- | ------------------------------------------------------------ |
| mch_id           | true     | String | 441649692783284224               | Merchants allocated by BitFS.                                |
| customer_id      | false    | String | 442314630598103040               | Scan code transaction user ID. When the user scans the code to get the order, the Field Name is returned. |
| out_trade_no     | true     | String | 7faf7e60a92d4afa963b83933a949ecc | The order number within the merchant system, within 32 characters, may contain letters. |
| nonce_str        | true     | String | FEC838C0BEA5468A82E2467DA4F70B8C | Random string.                                               |
| total_amount     | true     | String | 14.14                            | Merchant requested transaction amount: when fee_type is fiat currency, the unit is yuan; when fee_type is digital currency, the unit is 1. |
| transaction_id   | true     | String | 44240523622d4b2ca836176cd88085d3 | Order number generated by BitFS.                             |
| trade_type       | true     | String | WITHDRAW                         | Transaction type: Deposit: DEPOSIT; Withdraw: WITHDRAW.      |
| fee_type         | true     | String | CNY                              | The currency of the transaction that initiated the request: divided into legal currency and digital currency, see the list of legal currencies for details. |
| tick_price       | true     | String | 7.00                             | The price of BitFS when initiating the request.              |
| order_fee        | true     | String | 2.02                             | The number of digital currencies (USDT) actually traded.     |
| attach           | false    | String | "Recharge of Guangzhou Branch"   | Business extensions.                                         |
| trade_state      | true     | String | 100                              | Transaction status: 100 transaction success; 200 transaction failure; 300 transaction cancellation. |
| trade_state_desc | true     | String | Cancel Transaction               | A description of the transaction status.                     |
| sign             | true     | String | F752ABD95162A4A95E7C4A5E33DAEDD9 | Sign.                                                        |

### Error Code

| Name                   | Description                           | Reason                                                       | Solution                                                     |
| ---------------------- | ------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| APPKEY_MCHID_NOT_MATCH | machId does not match Merchant AppKey | machId does not match Merchant AppKey                        | Please confirm that appid and mch_id match.                  |
| SIGNERROR              | Sign error                            | Parameter Sign result is incorrect                           | Please check whether Sign parameters and methods meet the requirements of Sign algorithm. |
| LACK_PARAMS            | Missing parameters                    | Missing required request parameters                          | Please check if the parameters are complete.                 |
| SYSTEMERROR            | System error                          | System timeout                                               | The system is abnormal, please call again with the same parameters. |
| ORDERNOTEXIST          | Order number does not exist           | This transaction order number does not exist in the query system | The API can only check the merchant order returned by submitting the transaction, please check whether the Merchant Order Number to be queried is correct. |
