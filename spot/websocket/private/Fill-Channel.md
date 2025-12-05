# Fill Channel

### Description[​](#description "Direct link to Description")

Trade Details channel

Request

```json
{  
    "op": "subscribe",  
    "args": [  
        {  
            "instType": "SPOT",  
            "channel": "fill",  
            "instId": "default"  
        }  
    ]  
}
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| op | String | Yes | Operation, subscribe unsubscribe |
| arg | Object | Yes | Subscribed channels |
| > channel | String | Yes | Channel name: `fill` |
| > instType | String | Yes | Product type `SPOT` |
| > instId | String | No | Product ID or default |

Response

```json
{  
    "event": "subscribe",  
    "arg": {  
        "instType": "SPOT",  
        "channel": "fill",  
        "instId": "default"  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| event | String | Event |
| arg | Object | Subscribed channels |
| > channel | String | Channel name: fill |
| > instType | String | Product type `SPOT` |
| > instId | String | Product ID/default |
| code | String | Error code |
| msg | String | Error message |

Push Data

```json
{  
    "action":"snapshot",  
    "arg":{  
        "instType":"SPOT",  
        "channel":"fill",  
        "instId":"default"  
    },  
    "data":[  
        {  
            "orderId":"111",  
            "tradeId":"111",  
            "symbol":"BTCUSDT",  
            "orderType":"limit",  
            "side":"buy",  
            "priceAvg":"42740.41",  
            "size":"0.0006",  
            "amount":"25.644246",  
            "tradeScope":"marker",  
            "feeDetail":[  
                {  
                    "feeCoin":"USDT",  
                    "deduction":"no",  
                    "totalDeductionFee":"0",  
                    "totalFee":"0.01538655"  
                }  
            ],  
            "cTime":"1703580202094",  
            "uTime":"1703580202094"  
        },  
        {  
            "orderId":"111",  
            "tradeId":"222",  
            "symbol":"BTCUSDT",  
            "orderType":"limit",  
            "side":"buy",  
            "priceAvg":"42741.46",  
            "size":"0.0006",  
            "amount":"25.644876",              
            "tradeScope":"marker",  
            "feeDetail":[  
                {  
                    "feeCoin":"USDT",  
                    "deduction":"no",  
                    "totalDeductionFee":"0",  
                    "totalFee":"0.01538693"  
                }  
            ],  
            "cTime":"1703580202094",  
            "uTime":"1703580202094"  
        }  
    ],  
    "ts":1703580202416  
}
```

### Push Parameters[​](#push-parameters "Direct link to Push Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| action | String | Push action `snapshot` |
| arg | Object | Channels with successful subscription |
| > channel | String | Channel name: fill |
| > instType | String | Product type `SPOT` |
| > instId | String | Product ID |
| data | List<Object> | Subscription data |
| > orderId | String | Order ID |
| > tradeId | String | Trade ID |
| > symbol | String | Symbol |
| > orderType | String | Order type: `limit` `market` |
| > side | String | Order direction `buy`  `sell` |
| > priceAvg | String | Total average filled price |
| > size | String | Filled size |
| > amount | String | Accumulated filled size |
| > tradeScope | String | The liquidity direction of the latest transaction `taker`   `maker` |
| > feeDetail | List<Object> | Transaction fee of the order |
| >> deduction | String | deduction `yes`  `no` |
| >> totalDeductionFee | String | Fee of deduction |
| >> totalFee | String | Fee of all |
| >> feeCoin | String | Currency of transaction fee |
| > cTime | String | Create Time，milliseconds format of Unix timestamp, e.g.1597026383085 |
| > uTime | String | Update Time，milliseconds format of Unix timestamp, e.g.1597026383085 |