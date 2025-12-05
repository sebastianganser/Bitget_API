# SharkFin Subscription Result

Frequency limit: 5c/1s (Uid)

### Description[​](#description "Direct link to Description")

Get sharkfin subscription result

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/earn/sharkfin/subscribe-result

Request Example

```json
curl "https://api.bitget.com/api/v2/earn/sharkfin/subscribe-result?orderId=123123123" \  
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
| orderId | String | Yes | Order ID |

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
| result | String | Is the subscription successful `success` Success  `fail` Fail |
| msg | String | There will be an error message when the result is `fail` |