# Candlestick Channel

### Description[​](#description "Direct link to Description")

Get the candlestick data of the product

* When there are transactions in the K-line channel, data is pushed once per second.
* When there are no transactions, data is pushed once at the specified time granularity.

Request

```json
{  
    "op": "subscribe",  
    "args": [  
        {  
            "instType": "spot",  
            "topic": "kline",  
            "symbol": "BTCUSDT",  
            "interval": "1m"  
        }  
    ]  
}
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| op | String | Yes | Action   `subscribe` Subscribe   `unsubscribe` Unsubscribe |
| args | List<Object> | Yes | Subscribed channel |
| > instType | String | Yes | Product type `spot` Spot trading `usdt-futures` USDT futures   `coin-futures` Coin-M futures   `usdc-futures` USDC futures |
| > topic | String | Yes | Topic   `kline` K-line channel |
| > symbol | String | Yes | Symbol name   e.g., `BTCUSDT` |
| > interval | String | Yes | Interval   `1m`, `3m`,`5m`, `15m`, `30m`, `1H`, `4H`,`6H`, `12H`, `1D` |

Response

```json
{  
  "event": "subscribe",  
  "arg": {  
    "instType": "spot",  
    "topic": "kline",  
    "symbol": "BTCUSDT",  
    "interval": "1m"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameters | Type | Description |
| --- | --- | --- |
| event | String | Action   `subscribe` Subscribe   `unsubscribe` Unsubscribe   `error` Parameter error |
| arg | Object | Subscribed channel |
| > instType | String | Product type `spot` Spot trading `usdt-futures` USDT futures   `coin-futures` Coin-M futures   `usdc-futures` USDC futures |
| > topic | String | Topic   `kline` K-line channel |
| > symbol | String | Symbol name   e.g., `BTCUSDT` |
| > interval | String | Interval |
| code | String | Error code |
| msg | String | Error message |

Push

```json
{  
  "data": [  
    {  
      "volume": "0.423",  
      "high": "400005",  
      "low": "276670",  
      "start": "1710518400000",  
      "close": "400005",  
      "turnover": "148190.38375",  
      "open": "276670"  
    }  
  ],  
  "arg": {  
    "instType": "spot",  
    "symbol": "BTCUSDT",  
    "topic": "kline",  
    "interval": "1D"  
  },  
  "action": "snapshot",  
  "ts": 1736370735556  
}
```

### Push Parameters[​](#push-parameters "Direct link to Push Parameters")

| Parameters | Type | Description |
| --- | --- | --- |
| arg | Object | Subscribed channel |
| > instType | String | Product type `spot` Spot trading `usdt-futures` USDT futures   `coin-futures` Coin-M futures   `usdc-futures` USDC futures |
| > topic | String | Topic   `kline` |
| > symbol | String | Symbol name |
| action | String | Push data action   `snapshot` Full data   `update` Incremental data |
| data | List<String> | Subscribed data |
| > start | String | The timestamp that the system generated the data  A Unix timestamp in milliseconds |
| > open | String | Open price |
| > close | String | Close price |
| > high | String | Highest price |
| > low | String | Lowest price |
| > volume | String | Trade Volume *The unit is base coin* |
| > turnover | String | Turnover *The unit is base coin* |