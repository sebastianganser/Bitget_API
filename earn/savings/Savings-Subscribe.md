# Subscribe Savings

Frequency limit: 10c/1s (Uid)

### Description[​](#description "Direct link to Description")

Subscribe savings

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/earn/savings/subscribe

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/earn/savings/subscribe" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*******" \  
  -H "ACCESS-PASSPHRASE:*****" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json" \  
  -d '{"periodType":"flexible","productId":"23123123","amount":"99999999"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| productId | String | Yes | Product ID |
| periodType | String | Yes | Period type  `flexible` flexible period  `fixed` fixed period |
| amount | String | Yes | Subscribe amount |

Response Example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1748783837837,  
  "data": {  
    "orderId": "1313060074239184896"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| orderId | String | Successful subscription order ID |