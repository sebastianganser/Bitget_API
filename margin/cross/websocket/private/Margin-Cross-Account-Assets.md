# Cross-Margin Account Channel

### Description[​](#description "Direct link to Description")

Request Example

```json
{  
    "args":[  
        {  
            "channel":"account-crossed",  
            "coin":"default",  
            "instType":"MARGIN"  
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
| > instType | String | Yes | Product type: `MARGIN` |
| > channel | String | Yes | Channel name: `account-crossed` |
| > coin | String | Yes | Coin name，`default` represents all the coins，Only default is supported nows |

Response Example

```json
{  
    "event":"subscribe",  
    "arg":{  
        "instType":"MARGIN",  
        "channel":"account-crossed",  
        "coin":"default"  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| event | String | Event |
| arg | Object | Subscribed channels |
| > instType | String | Product type: `MARGIN` |
| > channel | String | Channel name: `account-crossed` |
| > coin | String | `default` |
| code | String | Error code, returned only on error |
| msg | String | Error message |

Push Data

```json
{  
    "action":"snapshot",  
    "arg":{  
        "instType":"MARGIN",  
        "channel":"account-crossed",  
        "coin":"default"  
    },  
    "data":[  
        {  
            "uTime":"1695881380854",  
            "id":"1",  
            "coin":"USDT",  
            "available":"31092.45075078",  
            "borrow":"0.00000000",  
            "frozen":"6.00000000",  
            "interest":"0.00000000",  
            "coupon":"0.00000000"  
        },  
        {  
            "uTime":"1695881380854",  
            "id":"1",  
            "coin":"BTC",  
            "available":"0.00000000",  
            "borrow":"0.99990096",  
            "frozen":"0.00000000",  
            "interest":"0.00416626",  
            "coupon":"0.00000000"  
        }  
    ],  
    "ts":1695881380856  
}
```

### Push Data Parameters[​](#push-data-parameters "Direct link to Push Data Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| arg | Object | Successful channel subscriptions |
| > instType | String | Product type: `MARGIN` |
| > channel | String | Channel name: `account-crossed` |
| > coin | String | `default` |
| action | String | Push data action, `snapshot` or `update` |
| data | List<Object> | Subscribed data |
| > available | String | Available amount |
| > borrow | String | Borrow amount |
| > coin | String | Coin name |
| > frozen | String | Amount frozen |
| > coupon | String | Coupon |
| > id | String | ID |
| > interest | String | Interest |
| > uTime | String | Updated time |