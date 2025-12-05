# Get OI Limit

### Description[​](#description "Direct link to Description")

get open interest limit.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/account/open-interest-limit
* Rate limit: 5/sec/UID

Request

```json
curl "https://api.bitget.com/api/v3/account/open-interest-limit?category=USDT-FUTURES&symbol=BTCUSDT" \  
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
| symbol | String | Yes | Symbol  e.g.,`BTCUSDT` |
| category | String | Yes | Product type   `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1764170997805,  
  "data": {  
    "symbol": "BTCUSDT",  
    "singleUserLimit": "2766.30748",  
    "masterSubLimit": "9173.8782",  
    "marketMakerLimit": "0"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| symbol | String | Symbol name |
| singleUserLimit | String | Single User Limit Quantity. |
| masterSubLimit | String | Main/Sub-account Quantity Limit |
| marketMakerLimit | String | Market Maker Total Quota |