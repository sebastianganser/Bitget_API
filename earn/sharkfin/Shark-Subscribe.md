# Subscribe SharkFin

Frequency limit: 10c/1s (Uid)

### Description[​](#description "Direct link to Description")

Subscribe sharkfin

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/earn/sharkfin/subscribe

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/earn/sharkfin/subscribe" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*******" \  
  -H "ACCESS-PASSPHRASE:*****" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json" \  
  -d '{"productId":"23123123","amount":"99999999"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| productId | String | Yes | Product ID |
| amount | String | Yes | Subscription amount |

Response Example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1696751519392,  
    "data": {  
        "orderId": "123123123",  
        "status": "2000.000000"  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| orderId | String | Order Id |
| status | String | Order status |