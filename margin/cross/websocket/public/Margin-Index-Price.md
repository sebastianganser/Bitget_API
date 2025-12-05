# Margin Index Price

### Description[​](#description "Direct link to Description")

Subscribe margin trading pair index price

Request Example

```json
{  
    "args":[  
        {  
            "channel":"index-price",  
            "instType":"MARGIN",  
            "instId":"default"  
        }  
    ],  
    "op":"subscribe"  
}
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| op | String | Yes | Operation subscribe Subscribe unsubscribe Unsubscribe |
| args | List<Object> | Yes | List of channels to request subscription |
| > instType | String | Yes | Product type: MARGIN |
| > channel | String | Yes | Channel name |
| > instId | String | Yes | Product ID Only support: `defualt`(all symbols) |

Response Example

```json
{  
    "event":"subscribe",  
    "arg":{  
        "instType":"MARGIN",  
        "channel":"index-price",  
        "instId":"default"  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| event | String | Event |
| arg | Object | Subscribed channels |
| > instType | String | Product type: MARGIN |
| > channel | String | Channel name |
| > instId | String | Product ID `default` |
| code | String | Error code, returned only on error |
| msg | String | Error message |

Push Data

```json
{  
    "action":"snapshot",  
    "arg":{  
        "instType":"MARGIN",  
        "channel":"index-price",  
        "instId":"default"  
    },  
    "data":[  
        {  
            "symbol":"BTCUSDT",  
            "baseCoin":"BTC",  
            "quoteCoin":"USDT",  
            "indexPrice":"25702.4",  
            "ts":"1695880514609"  
        }  
    ],  
    "ts":1695880514622  
}
```

### Push Parameters[​](#push-parameters "Direct link to Push Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| arg | Object | Channels with successful subscription |
| > instType | String | Product type: MARGIN |
| > channel | String | Channel name |
| > instId | String | Product ID |
| action | String | Push data action, `snapshot` or `update` |
| data | List<Object> | Subscribed data |
| > baseCoin | String | Base currency |
| > indexPrice | String | Index price |
| > quoteCoin | String | Quote currency |
| > symbol | String | Trading pair |
| > ts | String | > timestamp |