# Redeem Savings

Frequency limit: 10c/1s (Uid)

### Description[​](#description "Direct link to Description")

Redeem savings

* The interval of each redeem should be more than 1min, or it would return error

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/earn/savings/redeem

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/earn/savings/redeem" \  
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
| orderId | String | No | Assets Order ID   get this for `/assets` orderId |
| periodType | String | Yes | Period type  `flexible` flexible period  `fixed` fixed period |
| amount | String | Yes | Subscribe amount |

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
| orderId | String | Redemption successful order ID |
| status | String | order status |