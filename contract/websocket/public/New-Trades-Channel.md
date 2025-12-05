# Public Trade Channel

### Description[​](#description "Direct link to Description")

Get the public trade data(taker orders)

Real-time Push

Request Example

```json
{  
    "op": "subscribe",  
    "args": [  
        {  
            "instType": "USDT-FUTURES",  
            "channel": "trade",  
            "instId": "BTCUSDT"  
        }  
    ]  
}
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| op | String | Yes | Operation, subscribe unsubscribe |
| args | List<Object> | Yes | op list |
| > instType | String | Yes | Product type `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures |
| > channel | String | Yes | Channel, `trade` |
| > instId | String | Yes | Product ID e.g: ETHUSDT |

Response Example

```json
{  
    "event": "subscribe",  
    "arg": {  
        "instType": "USDT-FUTURES",  
        "channel": "trade",  
        "instId": "BTCUSDT"  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| event | String | event |
| arg | Object | arg list |
| > instType | String | Product type `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures |
| > channel | String | Channel, `trade` |
| > instId | String | Symbol name e.g: ETHUSDT |
| code | String | Error code |
| msg | String | Error message |

Push Data

```json
{  
    "action": "snapshot",  
    "arg": {  
        "instType": "USDT-FUTURES",  
        "channel": "trade",  
        "instId": "BTCUSDT"  
    },  
    "data": [  
        {  
            "ts": "1695716760565",  
            "price": "27000.5",  
            "size": "0.001",  
            "side": "buy",  
            "tradeId": "1111111111"  
        },  
        {  
            "ts": "1695716759514",  
            "price": "27000.0",  
            "size": "0.001",  
            "side": "sell",  
            "tradeId": "1111111111"  
        }  
    ],  
    "ts": 1695716761589  
}
```

### Push Parameters[​](#push-parameters "Direct link to Push Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| action | String | action |
| arg | Object | arg |
| > instType | String | Product type `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures |
| > channel | String | Channel, `trade` |
| > instId | String | Symbol: ETHUSDT |
| data | List<Object> | Data |
| > ts | String | Fill time: 1597026383085 |
| > price | String | Filled price |
| > size | String | Filled amount |
| > side | String | Filled side, sell/buy |
| > tradeId | String | tradeId |