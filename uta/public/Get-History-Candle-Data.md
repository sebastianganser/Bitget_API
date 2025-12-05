# Get Kline/Candlestick History

### Description[​](#description "Direct link to Description")

Query historical Kline/candlestick data within the last 90 days.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/market/history-candles
* Rate limit: 20/sec/IP

Request

```json
curl "https://api.bitget.com/api/v3/market/history-candles?category=USDT-FUTURES&symbol=BTCUSDT&granularity=3D&limit=10"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| category | String | Yes | Product Type `SPOT` Spot trading `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures |
| symbol | String | Yes | Symbol name  e.g.,`BTCUSDT` |
| interval | String | Yes | Granularity `1m`,`3m`,`5m`,`15m`,`30m`,`1H`,`4H`,`6H`,`12H`,`1D` |
| startTime | String | No | Start timestamp  A Unix millisecond timestamp, e.g.,`1672410780000` Request data after this start time (the maximum time query range is 90 days) |
| endTime | String | No | End timestamp  A Unix millisecond timestamp, e.g.,`1672410781000` Request data before this end time (the maximum time query range is 90 days) |
| type | String | No | Candlestick type  `market`, `mark`, `index`, `premium`. Default: `market` |
| limit | String | No | Limit per page   Default:`100`. Maximum: `100` |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1695865864944,  
  "data": [  
    [  
      "1687708800000",  
      "27176.93",  
      "27177.43",  
      "27166.93",  
      "27177.43",  
      "2990.08",  
      "81246917.3294"  
    ],  
    [  
      "1688313600000",  
      "27177.43",  
      "27177.43",  
      "24000",  
      "24001",  
      "2989.1",  
      "72450031.0448"  
    ]  
  ]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| >index[0] | String | The timestamp that the system generated the data |
| >index[1] | String | Open price |
| >index[2] | String | Highest price |
| >index[3] | String | Lowest price |
| >index[4] | String | Close price |
| >index[5] | String | Volume. *The unit is base coin* |
| >index[6] | String | Turnover. *The unit is quote coin* |