# ADL Notification Channel

### Description[​](#description "Direct link to Description")

Adl Notification Channel

Request Example

```json
{  
    "op": "subscribe",  
    "args": [  
        {  
            "instType": "UTA",  
            "topic": "adl-notificatio"  
        }  
    ]  
}
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| op | String | Yes | Operation   `subscribe`/`unsubscribe` |
| args | List<Object> | Yes | Subscribed channels |
| > instType | String | Yes | Product type `UTA` Unified trading account |
| > topic | String | Yes | Topic   `adl-notification` ADL Notification |

Response Example

```json
{  
  "event": "subscribe",  
  "arg": {  
    "instType": "UTA",  
    "topic": "adl-notification"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameters | Type | Description |
| --- | --- | --- |
| event | String | Operation  `subscribe` / `unsubscribe` / `error` |
| arg | Object | Subscribed channel |
| > instType | String | Product type  `UTA` |
| > topic | String | Topic  `adl-notification` ADL Notification |
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
    "instType": "UTA",  
    "topic": "adl-notification"  
  },  
  "action": "update",  
  "ts": 1740546523244  
}
```

### Push Parameters[​](#push-parameters "Direct link to Push Parameters")

| Parameters | Type | Description |
| --- | --- | --- |
| arg | Object | Subscribed channel |
| > instType | String | product type  `UTA` Unified trading account |
| > topic | String | Topic  `adl-notification` ADL Notification |
| action | String | Action  `snapshot` Full data  `update` Incremental data |
| data | List<String> | Subscribed data |
| >symbol | String | Symbol name |
| >side | String | Position side  `buy`Buy `sell`Sell |
| >status | String | ADL status  `triggered`Triggered |
| >price | String | ADL execution price |
| >amount | String | ADL execution amount |
| >ts | String | ADL start time (Unix millisecond timestamp) |