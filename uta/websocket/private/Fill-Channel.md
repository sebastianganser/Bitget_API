# Fill

### Description[​](#description "Direct link to Description")

Push real-time fill data.

Push rules:

1. No push on first-time subscription
2. Push when spot/leveraged/futures orders are filled

Request Example

```json
{  
    "op": "subscribe",  
    "args": [  
        {  
            "instType": "UTA",  
            "topic": "fill"  
        }  
    ]  
}
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameters | Type | Description |
| --- | --- | --- |
| op | String | Operation:   `subscribe` /`unsubscribe` |
| args | List<Object> | Subscribed channel |
| > instType | String | Product type `UTA` Unified trading account |
| > topic | String | Topic  `fill` |

Response Example

```json
{  
    "event": "subscribe",  
    "arg": {  
        "instType": "UTA",  
        "topic": "fill"  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameters | Type | Description |
| --- | --- | --- |
| event | String | Operation  `subscribe` / `unsubscribe` / `error` |
| arg | Object | Subscribed channel |
| > instType | String | Product type  `UTA` |
| > topic | String | Topic  `fill` |
| code | String | Error code |
| msg | String | Error message |

Push Data

```json
{  
  "data": [  
    {  
      "symbol": "BTCUSDT",  
      "orderType": "market",  
      "updatedTime": "1736378720623",  
      "side": "buy",  
      "orderId": "1288888888888888888",  
      "execPnl": "0",  
      "feeDetail": [  
        {  
          "feeCoin": "USDT",  
          "fee": "0.569958"  
        }  
      ],  
      "execTime": "1736378720623",  
      "tradeScope": "taker",  
      "tradeSide": "open",  
      "execId": "1288888888888888888",  
      "execLinkId": "1288888888888888888",  
      "execPrice": "94993",  
      "holdSide": "long",  
      "execValue": "949.93",  
      "category": "USDT-FUTURES",  
      "execQty": "0.01",  
      "clientOid": "1288888888888888889"  
    }  
  ],  
  "arg": {  
    "instType": "UTA",  
    "topic": "fill"  
  },  
  "action": "snapshot",  
  "ts": 1733904123981  
}
```

### Push Parameters[​](#push-parameters "Direct link to Push Parameters")

| Parameters | Type | Description |
| --- | --- | --- |
| arg | Object | Subscribed channel |
| > instType | String | product type  `UTA` Unified trading account |
| > topic | String | Topic  `fill` fill |
| action | String | Action  `snapshot` Full data  `update` Incremental data |
| data | List<String> | Subscribed data |
| > category | String | Product type   `SPOT` Spot trading   `MARGIN` Margin trading   `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures |
| > orderId | String | Order ID |
| > clientOid | String | Client Order ID |
| > execld | String | Fill ID |
| > execLinkId | String | Execution correlation ID |
| > symbol | String | Symbol name |
| > orderType | String | Order type  `limit`/`market` |
| > side | String | Trade side `buy`/`sell` |
| > holdSide | String | Position direction  `long`: Long  `short`: Short |
| > tradeSide | String | Trade side  `open`/`close`  Detailed enumerations can be obtained on the Enumeration page. |
| > execPrice | String | Fill price |
| > execQty | String | Fill quantity *The unit is base coin* |
| > execValue | String | Fill value *The unit is quote coin* |
| > execPnl | String | Execution profit and loss |
| > tradeScope | String | Trade scope `taker`/`maker` |
| > feeDetail | String | Fee detail |
| >> feeCoin | String | Fee coin |
| >> fee | String | Total fee |
| > execTime | String | Execution timestamp  A Unix timestamp in milliseconds. e.g.,`1736388000` |
| > updatedTime | String | Updated timestamp A Unix timestamp in milliseconds. e.g.,`1736388000` |