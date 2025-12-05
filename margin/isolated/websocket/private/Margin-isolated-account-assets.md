# Isolated-Margin Account Channel

### Description[​](#description "Direct link to Description")

Request Example

```json
{  
    "args":[  
        {  
            "channel":"account-isolated",  
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
| > instType | String | Yes | Product type: MARGIN |
| > channel | String | Yes | Channel name |
| > coin | String | Yes | Coin name，`default` represents all the coins，Only default is supported now |

Response Example

```json
{  
    "event":"subscribe",  
    "arg":{  
        "instType":"MARGIN",  
        "channel":"account-isolated",  
        "coin":"default"  
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
| > coin | String | `default` |
| code | String | Error code, returned only on error |
| msg | String | Error message |

Push Data

```json
{  
  "action":"snapshot",  
  "arg":{  
    "instType":"MARGIN",  
    "channel":"account-isolated",  
    "coin":"default"  
  },  
  "data":[  
    {  
      "uTime":"1695881380876",  
      "id":"1",  
      "coin":"USDT",  
      "symbol":"BTCUSDT",  
      "available":"989.4502207",  
      "borrow":"0",  
      "frozen":"0",  
      "interest":"0",  
      "coupon":"0"  
    },  
    {  
      "uTime":"1695881380876",  
      "id":"1000000002",  
      "coin":"BTC",  
      "symbol":"BTCUSDT",  
      "available":"0.00039814",  
      "borrow":"0",  
      "frozen":"0",  
      "interest":"0",  
      "coupon":"0"  
    },  
    {  
      "uTime":"1695881380876",  
      "id":"1000000001",  
      "coin":"USDT",  
      "symbol":"ETHUSDT",  
      "available":"9607383.17171658",  
      "borrow":"0",  
      "frozen":"0",  
      "interest":"0",  
      "coupon":"0"  
    },  
    {  
      "uTime":"1695881380876",  
      "id":"1000000000",  
      "coin":"ETH",  
      "symbol":"ETHUSDT",  
      "available":"2.5574646",  
      "borrow":"0",  
      "frozen":"0",  
      "interest":"0",  
      "coupon":"0"  
    }  
  ],  
  "ts":1695881380876  
}
```

### Push Data Parameters[​](#push-data-parameters "Direct link to Push Data Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| arg | Object | Successful channel subscriptions |
| > instType | String | Product type |
| > channel | String | Channel name |
| > coin | String | `default` |
| action | String | Push data action, `snapshot` or `update` |
| data | List<Object> | Subscribed data |
| > available | String | Available amount |
| > borrow | String | Borrow amount |
| > symbol | String | Trading pair |
| > coin | String | Coin name |
| > frozen | String | Amount frozen |
| > id | String | ID |
| > interest | String | Interest |
| > uTime | String | Updated time, ms |
| > coupon | String | Coupon |