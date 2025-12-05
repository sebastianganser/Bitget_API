# Repay

### Description[​](#description "Direct link to Description")

This endpoint enables manual repayment in the Unified Trading Account.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v3/account/repay
* Rate limit: 5/sec/UID
* Permission: UTA mgt. (read & write)

Request

```json
curl -X POST "https://api.bitget.com/api/v3/account/repay" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json" \  
   -d '{"repayableCoinList":["USDT"],"paymentCoinList":["ETH"]}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| repayableCoinList | Array | Yes | Repayable coin list |
| > index [0] | String | Yes | Repayable coin name e.g.,`USDT` |
| paymentCoinList | Array | Yes | Payment coin list |
| > index [0] | String | Yes | Payment coin name e.g.,`ETH` |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1728625799912,  
  "data": {  
    "result": "YES",  
    "repayAmount":"4345"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| result | String | Repayment result `YES`/`NO` |
| repayAmount | String | Repayment amount |