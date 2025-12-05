# Savings Redemption Results

Frequency limit: 10c/1s (Uid)

### Description[​](#description "Direct link to Description")

Get savings redeem result

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/earn/savings/redeem-result

Request Example

```json
curl "https://api.bitget.com/api/v2/earn/savings/redeem-result?orderId=123123&periodType=flexible" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*******" \  
  -H "ACCESS-PASSPHRASE:*****" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| orderId | String | Yes | subscription order ID |
| periodType | String | Yes | Period type  `flexible` flexible current  `fixed` fixed term |

Response Example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1696752594890,  
    "data": {  
        "result": "success",  
        "msg": ""  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| result | String | Redemption result  `success` Success  `fail` Fail |
| msg | String | There will be an error message when the result is `fail` |