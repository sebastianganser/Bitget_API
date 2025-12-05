# Get transferable amount

Rate limit: 5 req/sec/UID

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/spot/ins-loan/transfered

Request Example

```json
curl "https://api.bitget.com/api/v2/spot/ins-loan/transfered?coin=xxx" \  
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
| userId | String | No | User Id (Master account or sub-accounts) |
| coin | String | Yes | Coin name |

Response Example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1711697588556,  
  "data": {  
    "coin": "USDT",  
    "transfered": "1223",  
    "userId": "xxxxxxxxxx"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| coin | String | Coin name |
| transfered | String | Transferred amount |
| userId | String | User Id |