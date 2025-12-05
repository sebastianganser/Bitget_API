# Get Max Transferable

### Description[​](#description "Direct link to Description")

Get the maximum transferable amount for the unified account.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/account/max-transferable
* Rate limit: 3/sec/UID
* Permission: UTA mgt. (read)

Request

```json
curl "https://api.bitget.com/api/v3/account/max-transferable?coin=USDT" \  
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
| coin | String | Yes | Coin name |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1730189435812,  
  "data": {  
    "coin": "USDT",  
    "maxTransfer": "1",  
    "borrowMaxTransfer": "1"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameters | Type | Description |
| --- | --- | --- |
| coin | Array | Coin name |
| maxTransfer | String | Maximum transferable amount  unit: coin. |
| borrowMaxTransfer | String | Maximum transferable amount for borrowed coins  unit: coin. |