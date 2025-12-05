# Earn account

Frequency limit: 10c/1s (Uid)

### Description[​](#description "Direct link to Description")

Earn account overview

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/earn/account/assets

Request Example

```json
curl "https://api.bitget.com/api/v2/earn/account/assets" \  
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
| coin | String | No | assets coin |

Response Example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1712046333409,  
  "data": [  
    {  
      "coin": "BTC",  
      "amount": "0.10000000"  
    },  
    {  
      "coin": "USDT",  
      "amount": "400.00000000"  
    }  
  ]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| data | List<Object> | Savings assets list |
| > coin | String | coin |
| > amount | String | amount |