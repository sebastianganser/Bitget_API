# Account Channel

### Description[​](#description "Direct link to Description")

Get account information, push data according to the subscription dimensions for the first subscription.

Data will be pushed when the following events occurred:

1. Orders are filled
2. Transfer
3. Deposit
4. Withdrawal

Request Example

```json
{  
    "op": "subscribe",  
    "args": [  
        {  
            "instType": "SPOT",  
            "channel": "account",  
            "coin": "default"  
        }  
    ]  
}
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| op | String | Yes | Operation, subscribe unsubscribe |
| args | List<Object> | Yes | List of channels to request subscription |
| > instType | String | Yes | Product Type, `SPOT` |
| > channel | String | Yes | Channel name, `account` |
| > coin | String | Yes | Coin name，`default` represents all the coins，Only default is supported now |

Response Example

```json
{  
  "event": "subscribe",  
  "arg": {  
    "instType": "SPOT",  
    "channel": "account",  
    "coin": "default"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| event | String | Yes Event |
| arg | Object | Subscribed channels |
| > instType | String | Product Type, `SPOT` |
| > channel | String | Channel name, `account` |
| > coin | String | `default` |
| code | String | Error code, returned only on error |
| msg | String | Error message |

Push Data

```json
{  
    "action": "snapshot",  
    "arg": {  
        "instType": "SPOT",  
        "channel": "account",  
        "coin": "default"  
    },  
    "data": [  
        {  
            "coin": "USDT",  
            "available": "100000",  
            "frozen": "0",  
            "locked": "0",  
            "limitAvailable": "0",  
            "uTime":"1697092295506"  
        }  
    ],  
    "ts": 1695713887792  
}
```

### Push Parameters[​](#push-parameters "Direct link to Push Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| arg | Object | Channels with successful subscription |
| > instType | String | Product Type, `SPOT` |
| > channel | String | Channel name, `account` |
| > coin | String | `default` |
| action | String | Push data action, `snapshot` or `update` |
| data | List<Object> | Subscription data |
| > coin | String | Token name |
| > available | String | Available coin assets |
| > frozen | String | Amount of frozen assets Usually frozen when the order is placed |
| > locked | String | Amount of locked assets Locked assests required to become a fiat merchants, etc. |
| > limitAvailable | String | Restricted availability For spot copy trading |
| > uTime | String | Update time |