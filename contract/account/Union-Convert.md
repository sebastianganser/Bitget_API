# Union Convert

Rate limits: 1 time/1s (uid)

### Description[​](#description "Direct link to Description")

Union margin exchange

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/mix/account/union-convert

Request

```json
curl -X POST "https://api.bitget.com/api/v2/mix/account/union-convert" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json" \  
   -d '{"coin": "BTC","amount": "1"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| coin | String | Yes | Coin Name E.g., BTC |
| amount | String | Yes | Exchange Quantity Unit: Exchange Currency |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1627293357336,  
  "data": {  
    "usdtAmount": "1"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| usdtAmount | String | Exchanged USDT Quantity |