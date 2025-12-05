# Get Account Funding Assets

### Description[​](#description "Direct link to Description")

Obtain fund account information and only return the coins with assets.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/account/funding-assets
* Rate limit: 20/sec/UID
* Permission: UTA mgt. (read)

Request

```json
curl "https://api.bitget.com/api/v3/account/funding-assets" \  
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
| coin | String | No | Coin name |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1750396239013,  
  "data": [  
    {  
      "coin": "BGB",  
      "available": "0.01",  
      "frozen": "0",  
      "balance": "0.01"  
    },  
    {  
      "coin": "USDT",  
      "available": "0.04",  
      "frozen": "0",  
      "balance": "0.04"  
    }  
  ]  
}
```

### Response Example[​](#response-example "Direct link to Response Example")

| Parameters | Type | Description |
| --- | --- | --- |
| coin | String | Coin name |
| balance | String | Balance  Unit: the current asset coin |
| available | String | Available  Unit: the current asset coin |
| frozen | String | Frozen  Unit: the current asset coin |