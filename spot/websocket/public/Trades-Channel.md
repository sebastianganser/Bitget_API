# Trading Channel

### Description[​](#description "Direct link to Description")

Push once if any trade is matched(taker orders)

After first subscription, it will push the recent snapshot data and then push the update data

Real-time Push

Request Example

```json
{  
    "op": "subscribe",  
    "args": [  
        {  
            "instType": "SPOT",  
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
| args | List<Object> | Yes | List of channels to subscribe to |
| > instType | String | Yes | Product Line Type, `SPOT` |
| > channel | String | Yes | Channel name, `trade` |
| > instId | String | Yes | Product id For example: ETHUSDT |

Response Example

```json
{  
    "event": "subscribe",  
    "arg": {  
        "instType": "SPOT",  
        "channel": "trade",  
        "instId": "BTCUSDT"  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| event | String | Event, `subscribe` `unsubscribe` `error` |
| arg | Object | The channel subscribe to |
| > instType | String | product type, `SPOT` |
| > channel | String | Channel name, `trade` |
| > instId | String | Product id. For example: ETHUSDT |
| code | String | Error code, returned only on error |
| msg | String | Error message |

Push Data

```json
{  
    "action": "snapshot",  
    "arg": {  
        "instType": "SPOT",  
        "channel": "trade",  
        "instId": "BTCUSDT"  
    },  
    "data": [  
        {  
            "ts": "1695709835822",  
            "price": "26293.4",  
            "size": "0.0013",  
            "side": "buy",  
            "tradeId": "1000000000"  
        }  
    ],  
    "ts": 1695711090682  
}
```

### Push Parameters[​](#push-parameters "Direct link to Push Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| arg | Object | Successfully subscribed channel |
| > instType | String | Product Type, `SPOT` |
| > channel | String | Channel name, `trade` |
| > instId | String | Product id For example: ETHUSDT |
| action | String | Push data action, `snapshot` or `update` |
| data | List<Object> | Subscribed data |
| > tradeId | String | Transaction ID |
| > ts | String | Transaction time, millisecond format of Unix timestamp, such as 1597026383085 |
| > price | String | Transaction price |
| > size | String | Transaction quantity |
| > side | String | Transaction direction |