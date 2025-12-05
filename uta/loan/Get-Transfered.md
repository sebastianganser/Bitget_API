# Get Transferred Quantity

### Description[​](#description "Direct link to Description")

Get Transferred Quantity

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/ins-loan/transfered
* Rate limit: 3/sec/UID
* Permission: UTA mgt. (read)

Request

```json
curl "https://api.bitget.com/api/v3/ins-loan/transfered?coin=USDT" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| userId | String | No | User Id (Master account or sub-accounts) |
| coin | String | Yes | Coin |

Response

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

| Parameter | Type | Comments |
| --- | --- | --- |
| coin | String | Coin name |
| transfered | String | Transferred quantity |
| userId | String | User Id |