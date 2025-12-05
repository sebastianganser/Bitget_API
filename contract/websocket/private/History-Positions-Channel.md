# History Position Channel

Data will be pushed when the position totally closed

### Description[​](#description "Direct link to Description")

Subscribe the position channel

Data will be pushed when the position totally closed

Request Example

```json
{  
    "args":[  
        {  
            "channel":"positions-history",  
            "instId":"default",  
            "instType":"USDT-FUTURES"  
        }  
    ],  
    "op":"subscribe"  
}
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| op | String | Yes | subscribe unsubscribe |
| args | List<Object> | Yes | List of channels to request subscription |
| > channel | String | Yes | Channel name: `positions-history` |
| > instType | String | Yes | Product type `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures |
| > instId | String | Yes | Symbol name,`default`represents all the symbols，Only default is supported now |

Response Example

```json
{  
    "event":"subscribe",  
    "arg":{  
        "instType":"USDT-FUTURES",  
        "channel":"positions-history",  
        "instId":"default"  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| event | String | Event |
| arg | Object | Subscribed channels |
| > channel | String | Channel name: `positions-history` |
| > instType | String | Product type `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures |
| > instId | String | `default` |
| code | String | Error code |
| msg | String | Error message |

Push Data

```json
{  
    "action":"snapshot",  
    "arg":{  
        "instType":"USDT-FUTURES",  
        "channel":"positions-history",  
        "instId":"default"  
    },  
    "data":[  
        {  
            "posId":"1",  
            "instId":"BTCUSDT",  
            "marginCoin":"USDT",  
            "marginMode":"crossed",  
            "holdSide":"short",  
            "posMode":"one_way_mode",  
            "openPriceAvg":"20000.0",  
            "closePriceAvg":"26221.0",  
            "openSize":"0.010",  
            "closeSize":"0.010",  
            "achievedProfits":"-62.21000000",  
            "settleFee":"-0.02277989",  
            "openFee":"-0.12000000",  
            "closeFee":"-0.15732600",  
            "cTime":"1696907951177",  
            "uTime":"1697090609976"  
        }  
    ],  
    "ts":1697099840122  
}
```

### Push Parameters[​](#push-parameters "Direct link to Push Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| action | String | 'snapshot' |
| arg | Object | Channels with successful subscription |
| > channel | String | Channel name: `positions-history` |
| > instType | String | Product type `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures |
| > instId | String | `default` |
| data | List<Object> | Subscription data |
| > posId | String | Position ID |
| > instId | String | Product ID delivery contract reference：<https://www.bitget.com/api-doc/common/release-note> |
| > marginCoin | String | Currency of occupied margin |
| > marginMode | String | Margin mode `fixed`: isolated mode `crossed`: crossed mode |
| > holdSide | String | Position direction |
| > posMode | String | Position mode |
| > openPriceAvg | String | Average entry price |
| > closePriceAvg | String | Average close price |
| > openSize | String | Open size |
| > closeSize | String | Close size |
| > achievedProfits | String | Realized PnL |
| > settleFee | String | Settle fee |
| > openFee | String | Total open fee |
| > closeFee | String | Total close fee |
| > cTime | String | Position creation time, milliseconds format of Unix timestamp, e.g.1597026383085 |
| > uTime | String | Lastest position update time, milliseconds format of Unix timestamp, e.g.1597026383085 |