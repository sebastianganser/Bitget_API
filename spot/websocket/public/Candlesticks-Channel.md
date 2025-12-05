# Candlestick Channel

### Description[​](#description "Direct link to Description")

Get the candlestick data of the product

After first subscription, it will push the recent snapshot data and then push the update data

When there are transactions in the K-line channel, data is pushed once per second.

When there are no transactions, data is pushed once at the specified time granularity.

Request Example

```json
{  
    "op": "subscribe",  
    "args": [  
        {  
            "instType": "SPOT",  
            "channel": "candle1m",  
            "instId": "ETHUSDT"  
        }  
    ]  
}
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| op | String | Yes | Operation, subscribe unsubscribe |
| args | List<Object> | Yes | List of channels to request subscription |
| > instType | String | Yes | Product line type |
| > channel | String | Yes | Channel name, candle1m, candle5m 5 minutes, candle15 15 minutes, candle30m 30 minutes, candle1H 1 hour, candle4H 4 hours, candle6H 6 hours, candle12H 12 hours. candle1D 1 day, candle3D 3 days, candle1W 1 week, candle1M 1 month-line, candle6Hutc 6-hour line, UTC, candle12Hutc 12-hour line, UTC, candle1Dutc 1-day line, UTC candle3Dutc, UTC, 3-day line, candle1Wutc UTC, weekly line, candle1Mutc monthly line, UTC. |
| > instId | String | Yes | Product ID, e.g. ETHUSDT |

Response Example

```json
{  
  "event": "subscribe",  
  "arg": {  
    "instType": "SPOT",  
    "channel": "candle1m",  
    "instId": "ETHUSDT"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| event | String | Yes event, subscribe unsubscribe error |
| arg | Object | Subscribed channels |
| > instType | String | Product type |
| > channel | String | Channel name, candle1m, candle5m 5 minutes, candle15 15 minutes, candle30m 30 minutes, candle1H 1 hour, candle4H 4 hours, candle6H 6 hours, candle12H 12 hours. candle1D 1 day, candle3D 3 days, candle1W 1 week, candle1M 1 month-line, candle6Hutc 6-hour line, UTC, candle12Hutc 12-hour line, UTC, candle1Dutc 1-day line, UTC candle3Dutc, UTC, 3-day line, candle1Wutc UTC, weekly line, candle1Mutc monthly line, UTC. |
| > instId | String | Product ID, e.g. ETHUSDT |
| code | String | Error code, returned only on error |
| msg | String | Error message |

Push Data

```json
{  
  "action": "snapshot",  
  "arg": {  
    "instType": "SPOT",  
    "channel": "candle1m",  
    "instId": "ETHUSDT"  
  },  
  "data": [  
    [  
      "1695672780000",  
      "2200.1",  
      "2200.1",  
      "2200.1",  
      "2200.1",  
      "0",  
      "0",  
      "0"  
    ]  
  ],  
  "ts": 1695702747821  
}
```

### Push Parameters[​](#push-parameters "Direct link to Push Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| action | String | Push data action, `snapshot` or `update` |
| arg | Object | Subscribed channels |
| > channel | String | Channel name |
| > instType | String | Product type |
| > instId | String | Product ID, e.g. ETHUSDT |
| data | List<String> | Subscription data |
| > index[0] | String | Start time, milliseconds format of Unix timestamp, e.g.1597026383085 |
| > index[1] | String | Opening price |
| > index[2] | String | Highest price |
| > index[3] | String | Lowest price |
| > index[4] | String | Closing price |
| > index[5] | String | Trading volume of the coin |
| > index[6] | String | Trading volume of quote currency |
| > index[7] | String | Trading volume (USDT) |