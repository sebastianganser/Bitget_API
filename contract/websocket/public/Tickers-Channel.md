# Market Channel

### Description[​](#description "Direct link to Description")

Retrieve the latest traded price, bid price, ask price and 24-hour trading volume of the instruments. When there is
a change (deal, buy, sell, issue): 300ms to 400ms.

Request Example

```json
{  
    "op": "subscribe",  
    "args": [  
        {  
            "instType": "USDT-FUTURES",  
            "channel": "ticker",  
            "instId": "BTCUSDT"  
        }  
    ]  
}
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| op | String | Yes | Operation, subscribe unsubscribe |
| args | List<Object> | Yes | List of channels to request subscription |
| > instType | String | Yes | Product type |
| > channel | String | Yes | Channel name |
| > instId | String | Yes | Product ID E.g. ETHUSDT |

Response Example

```json
{  
    "event": "subscribe",  
    "arg": {  
        "instType": "USDT-FUTURES",  
        "channel": "ticker",  
        "instId": "BTCUSDT"  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| event | String | Event |
| arg | Object | Subscribed channels |
| > instType | String | Product type |
| > channel | String | Channel name |
| > instId | String | Product ID E.g. ETHUSDT |
| code | String | Error code |
| msg | String | Error message |

Push Data

```json
{  
    "action": "snapshot",  
    "arg": {  
        "instType": "USDT-FUTURES",  
        "channel": "ticker",  
        "instId": "BTCUSDT"  
    },  
    "data": [  
        {  
            "instId": "BTCUSDT",  
            "lastPr": "27000.5",  
            "bidPr": "27000",  
            "askPr": "27000.5",  
            "bidSz": "2.71",  
            "askSz": "8.76",  
            "open24h": "27000.5",  
            "high24h": "30668.5",  
            "low24h": "26999.0",  
            "change24h": "-0.00002",  
            "fundingRate": "0.000010",  
            "nextFundingTime": "1695722400000",  
            "markPrice": "27000.0",  
            "indexPrice": "25702.4",  
            "holdingAmount": "929.502",  
            "baseVolume": "368.900",  
            "quoteVolume": "10152429.961",  
            "openUtc": "27000.5",  
            "symbolType": 1,  
            "symbol": "BTCUSDT",  
            "deliveryPrice": "0",  
            "ts": "1695715383021"  
        }  
    ],  
    "ts": 1695715383039  
}
```

### Push Parameters[​](#push-parameters "Direct link to Push Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| arg | Object | Channels with successful subscription |
| > instType | String | Product type |
| > channel | String | Channel name |
| > instId | String | Product ID |
| action | String | Push data action, `snapshot` or `update` |
| data | List | Subscription data |
| > instId | String | Product ID, BTCUSDT |
| >lastPr | String | Latest price |
| >askPr | String | Ask price |
| >bidPr | String | Bid price |
| >high24h | String | 24h high |
| >low24h | String | 24h low |
| >change24h | String | 24h change |
| >fundingRate | String | Funding rate |
| >nextFundingTime | String | Next funding rate settlement time, Milliseconds format of timestamp Unix, e.g. 1597026383085 |
| >ts | String | System time, Milliseconds format of current data timestamp Unix, e.g. 1597026383085 |
| >markPrice | String | Mark price |
| >indexPrice | String | Index price |
| >holdingAmount | String | Open interest |
| >baseVolume | String | Trading volume of the coin |
| >quoteVolume | String | Trading volume of quote currency |
| >openUtc | String | Price at 00:00 (UTC) |
| >symbolType | Integer | SymbolType: 1->perpetual 2->delivery |
| >symbol | String | Trading pair |
| >deliveryPrice | String | Delivery price of the delivery futures, when symbolType = 1(perpetual) it is always 0 It will be pushed 1 hour before delivery |
| >bidSz | String | Buying amount |
| >askSz | String | selling amount |
| >open24h | String | Entry price of the last 24 hours, The opening time is compared on a 24-hour basis. i.e.: Now it is 7:00 PM of the 2nd day of the month, then the corresponding opening time is 7:00 PM of the 1st day of the month. |