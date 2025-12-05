# Get Open Interest

### Description[​](#description "Direct link to Description")

Query the total number of unsettled or open futures

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/market/open-interest
* Rate limit: 20/sec/IP

Request

```json
curl "https://api.bitget.com/api/v3/market/open-interest?category=USDT-FUTURES&symbol=BTCUSDT"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| category | String | Yes | Product Type `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures |
| symbol | String | No | Symbol name  e.g.,`BTCUSDT` |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1730969652387,  
  "data": {  
    "list": [  
      {  
        "symbol": "BTCUSDT",  
        "openInterest": "2243.019"  
      }  
    ],  
    "ts": "1730969652411"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| list | Array | Data list |
| >symbol | String | Symbol name |
| >openInterest | String | Open interest |
| ts | String | The timestamp that the system generated the data  A Unix timestamp in milliseconds |