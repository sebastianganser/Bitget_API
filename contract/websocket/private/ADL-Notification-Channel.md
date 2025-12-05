# ADL Notification Channel

### Description[​](#description "Direct link to Description")

Adl Notification Channel

Request Example

```json
{  
    "args": [  
        {  
            "channel": "adl-noti",  
            "instId": "default",  
            "instType": "USDT-FUTURES"  
        }  
    ],  
    "op": "subscribe"  
}
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| op | String | Yes | Operation, subscribe unsubscribe |
| args | List<Object> | Yes | List of channels to request subscription |
| > channel | String | Yes | Channel name: `adl-noti` |
| > instType | String | Yes | Product type `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures |
| > instId | String | No | Symbol Name  By default, subscribes to all symbols: default |

Response Example

```json
{  
  "event": "subscribe",  
  "arg": {  
    "instType": "USDT-FUTURES",  
    "channel": "adl-noti",  
    "instId": "default"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| event | String | Event |
| arg | Object | Subscribed channels |
| > channel | String | Channel name: `adl-noti` |
| > instType | String | Product type `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures |
| > instId | String | Symbol Name  By default, subscribes to all symbols: default |
| code | String | Error code |
| msg | String | Error message |

Push Data

```json
{  
  "data": [  
    {  
      "symbol": "BTCUSDT",  
      "side": "buy",  
      "status": "triggered",  
      "price": "88291.2",  
      "amount": "2.35",  
      "ts": "1740546523244"  
    }  
  ],  
  "arg": {  
    "instType": "USDT-FUTURES",  
    "channel": "adl-noti",  
    "instId": "default"  
  },  
  "action": "update",  
  "ts": 1740546523244  
}
```

### Push Parameters[​](#push-parameters "Direct link to Push Parameters")

| Parameters | Type | Description |
| --- | --- | --- |
| arg | Object | Channels with successful subscription |
| > channel | String | Channel name: `adl-noti` |
| > instType | String | Product type `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures |
| > instId | String | Symbol Name  By default, subscribes to all symbols: default |
| action | String | Action  `snapshot` Full data  `update` Incremental data |
| data | List<String> | Subscribed data |
| >symbol | String | Symbol name |
| >side | String | Position side  `buy`Buy `sell`Sell |
| >status | String | ADL status  `triggered`Triggered |
| >price | String | ADL execution price |
| >amount | String | ADL execution amount |
| >ts | String | ADL start time (Unix millisecond timestamp) |