# Get Open Interest Limit

### Description[​](#description "Direct link to Description")

Interface is used to get future contract OI Limit.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/market/oi-limit
* Rate Limit: 10 req/sec/IP

Request Example

```json
curl "https://api.bitget.com/api/v3/market/oi-limit?category=usdt-futures"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| symbol | String | No | Trading pair, based on the symbolName, i.e. BTCUSDT |
| category | String | Yes | Product type `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures |

Response Example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1741665165571,  
  "data": [{  
    "symbol": "BTCUSDT",  
    "notionalValue": "1000000",  
    "totalNotionalValue": "5000000"  
  },  
    {  
      "symbol": "ETHUSDT",  
      "notionalValue": "1000000",  
      "totalNotionalValue": "5000000"  
    }]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| > symbol | String | Product name |
| > notionalValue | String | Individual User Position Notional Value |
| > totalNotionalValue | String | Sub-account and Main-account Position Notional Value |