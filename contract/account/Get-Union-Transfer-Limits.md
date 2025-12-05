# Get Union Transfer Limits

Rate limits: 1 time/1s (uid)

### Description[​](#description "Direct link to Description")

Get union margin currency transfer limits

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/mix/account/transfer-limits

Request

```json
curl "https://api.bitget.com/api/v2/mix/account/transfer-limits" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| coin | String | Yes | Coin Name E.g., BTC |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1627293357336,  
  "data": {  
    "coin": "BTC",  
    "maxTransferIn": "100"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| coin | String | Coin Name |
| maxTransferIn | String | Maximum Transfer-in Quantity Unit: coin |