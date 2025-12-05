# Savings Subscription Result

Frequency limit: 10c/1s (Uid)

### Description[​](#description "Direct link to Description")

Get savings subscription info

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/earn/savings/subscribe-result

Request Example

```json
curl "https://api.bitget.com/api/v2/earn/savings/subscribe-result?orderId=123123&periodType=flexible" \  
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
| productId | String | Yes | Product ID |
| periodType | String | Yes | Period type  `flexible` flexible period  `fixed` fixed period |

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
| result | String | Subscription result  `success` Success   `fail` Fail |
| msg | String | There will be an error message when the result is `fail` |