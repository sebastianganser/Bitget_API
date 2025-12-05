# Market Channel

### Description[​](#description "Direct link to Description")

Get the product's latest price, bid price, bid price and 24h trading volume information. Frequency of data push: 200ms ~ 300ms

Request Example

```json
{  
    "op": "subscribe",  
    "args": [  
        {  
            "instType": "SPOT",  
            "channel": "ticker",  
            "instId": "ETHUSDT"  
        }  
    ]  
}
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| op | String | Yes | Operation, subscribe unsubscribe |
| args | Array | List<Object> | Yes List of channels to request subscription |
| > instType | String | Yes | Product line type |
| > channel | String | Yes | Channel name |
| > instId | String | Yes | Product ID, e.g. ETHUSDT |

Response Example

```json
{  
  "event": "subscribe",  
  "arg": {  
    "instType": "SPOT",  
    "channel": "ticker",  
    "instId": "ETHUSDT"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| event | String | Yes Event |
| arg | Object | Subscribed channels |
| > instType | String | Product type |
| > channel | String | Channel name |
| > instId | String | Product ID, e.g. ETHUSDT |
| code | String | Error code, returned only on error |
| msg | String | Error message |

Push Data

```json
{  
    "action": "snapshot",  
    "arg": {  
        "instType": "SPOT",  
        "channel": "ticker",  
        "instId": "ETHUSDT"  
    },  
    "data": [  
        {  
            "instId": "ETHUSDT",  
            "lastPr": "2200.10",  
            "open24h": "0.00",  
            "high24h": "0.00",  
            "low24h": "0.00",  
            "change24h": "0.00",  
            "bidPr": "1792",  
            "askPr": "2200.1",  
            "bidSz": "0.0084",  
            "askSz": "19740.8811",  
            "baseVolume": "0.0000",  
            "quoteVolume": "0.0000",  
            "openUtc": "0.00",  
            "changeUtc24h": "0",  
            "ts": "1695702438018"  
        }  
    ],  
    "ts": 1695702438029  
}
```

### Push Parameters[​](#push-parameters "Direct link to Push Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| arg | Object | Channels with successful subscription |
| > instType | String | Product type |
| > channel | String | Channel name |
| > instId | String | Product ID, e.g. ETHUSDT |
| action | String | Push data action: `snapshot` |
| data | List<Object> | Subscription data |
| > instId | String | Product ID, e.g. ETHUSDT |
| > lastPr | String | Latest price |
| > askPr | String | Ask price |
| > bidPr | String | Bid price |
| > open24h | String | Entry price of the last 24 hours |
| > high24h | String | 24h high |
| > low24h | String | 24h low |
| > baseVolume | String | 24h trading volume in left coin |
| > quoteVolume | String | 24h trading volume in right coin |
| > ts | String | Milliseconds format of data generation time Unix timestamp, e.g. 1597026383085 |
| > openUtc | String | UTC±00:00 Entry price |
| > changeUtc24h | String | Change at UTC+0, 0.01 means 1%. |
| > bidSz | String | Buying amount |
| > askSz | String | Selling amount |
| > change24h | String | 24-hour change, 0.01 means 1%. |