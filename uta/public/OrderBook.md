# Get OrderBook

### Description[​](#description "Direct link to Description")

Query order book depth data.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/market/orderbook
* Rate limit: 20/sec/IP

Request

```json
curl "https://api.bitget.com/api/v3/market/orderbook?category=USDT-FUTURES&symbol=BTCUSDT&limit=5"  \
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| category | String | Yes | Product Type `SPOT` Spot trading `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures |
| symbol | String | Yes | Symbol name  e.g.,`BTCUSDT` |
| limit | String | No | Limit per page  Default: `5`. Maximum: `200` |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1730969017897,  
  "data": {  
    "a": [  
      [  
        73000.0,  
        0.007  
      ],  
      [  
        74000.0,  
        0.007  
      ],  
      [  
        75000.0,  
        0.007  
      ],  
      [  
        75123.0,  
        5.615  
      ]  
    ],  
    "b": [  
      [  
        71213.8,  
        1.836  
      ],  
      [  
        71213.3,  
        10.000  
      ],  
      [  
        71212.8,  
        10.000  
      ]  
    ],  
    "ts": "1730969017964" // Match engine timestamp  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| a | Array | Sell Asks. Sort by price in ascending order |
| > Index 0 | String | Sell price |
| > Index 1 | String | Sell quantity |
| b | Array | Buy bids. Sort by price in descending order |
| > Index 0 | String | Buy Price |
| > Index 1 | String | Buy quantity |
| ts | String | The timestamp that the system generated data  A Unix timestamp in milliseconds |