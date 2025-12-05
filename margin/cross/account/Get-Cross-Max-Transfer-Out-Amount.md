# Get Cross Max Transferable

Frequency limit: 10 times/1s (UID)

### Description[​](#description "Direct link to Description")

Get max transferable

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/margin/crossed/account/max-transfer-out-amount

Request Example

```json
curl "https://api.bitget.com/api/v2/margin/crossed/account/max-transfer-out-amount?coin=USDT" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*******" \  
   -H "ACCESS-PASSPHRASE:*****" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json" \
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| coin | String | Yes | Token name |

Response Example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1695636742119,  
  "data": {  
    "coin": "USDT",  
    "maxTransferOutAmount": "11"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| coin | String | Coin |
| maxTransferOutAmount | String | Maximum transferable amount |