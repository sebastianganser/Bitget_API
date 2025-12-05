# Public Trades Channel

### Description[​](#description "Direct link to Description")

To subscribe the public trades channel

Real-time Push

Request

```json
{  
    "op": "subscribe",  
    "args": [  
        {  
            "instType": "usdt-futures",  
            "topic": "publicTrade",  
            "symbol": "BTCUSDT"  
        }  
    ]  
}
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameters | Type | Required | Description |
| --- | --- | --- | --- |
| op | String | Yes | Operation   `subscribe` Subscribe   `unsubscribe` Unsubscribe |
| args | List<Object> | Yes | Subscribed channel |
| > instType | String | Yes | Product type `spot` Spot trading `usdt-futures` USDT futures   `coin-futures` Coin-M futures   `usdc-futures` USDC futures |
| > topic | String | Yes | Topic   `publicTrade` Public trade |
| > symbol | String | Yes | Symbol name   e.g. `BTCUSDT` |

Response

```json
{  
  "event": "subscribe",  
  "arg": {  
    "instType": "usdt-futures",  
    "topic": "publicTrade",  
    "symbol": "BTCUSDT"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameters | Type | Description |
| --- | --- | --- |
| event | String | Operation   `subscribe` Subscribe   `unsubscribe` Unsubscribe   `error` Parameter error |
| arg | Object | Subscribed channel |
| > instType | String | Product type `spot` Spot trading `usdt-futures` USDT futures   `coin-futures` Coin-M futures   `usdc-futures` USDC futures |
| > topic | String | Topic   `publicTrade` Public trade channel |
| > symbol | String | Symbol name |
| code | String | Error code |
| msg | String | Error message |

Push

```json
{  
  "data": [  
    {  
      "p": "100000",  
      "S": "buy",  
      "T": "1736348770627",  
      "v": "0.00118",  
      "i": "1260903622036942849",  
      "L": "1234568787787878787"  
    }  
  ],  
  "arg": {  
    "instType": "usdt-futures",  
    "symbol": "BTCUSDT",  
    "topic": "publicTrade"  
  },  
  "action": "snapshot",  
  "ts": 1736371104297  
}
```

### Push Parameters[​](#push-parameters "Direct link to Push Parameters")

| Parameters | Type | Description |
| --- | --- | --- |
| arg | Object | Subscribed channel |
| > instType | String | Product type `spot` Spot trading `usdt-futures` USDT futures   `coin-futures` Coin-M futures   `usdc-futures` USDC futures |
| > topic | String | Topic   `publicTrade` |
| > symbol | String | Symbol name |
| action | String | Push data action   `snapshot` Full data   `update` Incremental data |
| data | List<String> | Subscribed data |
| > i | String | Fill execution ID |
| > L | String | Execution correlation ID |
| > p | String | Fill price |
| > v | String | Fill size |
| > S | String | Fill side   `sell`/`buy` |
| > T | String | Fill timestamp   A Unix timestamp in milliseconds |