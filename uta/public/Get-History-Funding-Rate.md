# Get Funding Rate History

### Description[​](#description "Direct link to Description")

Query historical funding rate records. The Funding interval varies by symbol and can be retrieved via the Instruments endpoint.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/market/history-fund-rate
* Rate limit: 20/sec/IP

Request

```json
curl "https://api.bitget.com/api/v3/market/history-fund-rate?category=USDT-FUTURES&symbol=BTCUSDT&limit=10&cursor=1" \
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| category | String | Yes | Product Type `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures |
| symbol | String | Yes | Symbol name  e.g.,`BTCUSDT` |
| cursor | String | No | Page number  Default: `1`. Maximum: `100` |
| limit | String | No | Limit per page  Default: `200`. Maximum: `200` |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1754908278922,  
  "data": {  
    "resultList": [  
      {  
        "symbol": "BTCUSDT",  
        "fundingRate": "0.0001",  
        "fundingRateTimestamp": "1754899200000"  
      },  
      {  
        "symbol": "BTCUSDT",  
        "fundingRate": "0.0001",  
        "fundingRateTimestamp": "1754870400000"  
      }  
    ]  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| resultList | List<Object> | Data list |
| > symbol | String | Symbol name |
| > fundingRate | String | Funding rate |
| > fundingRateTimestamp | String | Funding rate timestamp  A Unix timestamp in milliseconds |