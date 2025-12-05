# Position Channel

### Description[​](#description "Direct link to Description")

Subscribe the position channel

Data will be pushed when the following events occurred:

1. Open/Close orders are created
2. Open/Close orders are filled
3. Orders are canceled

Request Example

```json
{  
    "op": "subscribe",  
    "args": [  
        {  
            "instType": "USDT-FUTURES",  
            "channel": "positions",  
            "instId": "default"  
        }  
    ]  
}
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| op | String | Yes | Operation, subscribe unsubscribe |
| args | List<Object> | Yes | List of channels to request subscription |
| > channel | String | Yes | Channel name: `positions` |
| > instType | String | Yes | Product type `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures |
| > instId | String | Yes | Symbol name,`default`represents all the symbols，Only default is supported now |

Response Example

```json
{  
    "event": "subscribe",  
    "arg": {  
        "instType": "USDT-FUTURES",  
        "channel": "positions",  
        "instId": "default"  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| event | String | Event |
| arg | Object | Subscribed channels |
| > channel | String | Channel name: `positions` |
| > instType | String | Product type `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures |
| > instId | String | `default` |
| code | String | Error code |
| msg | String | Error message |

Push Data

```json
{  
    "action": "snapshot",  
    "arg": {  
        "instType": "USDT-FUTURES",  
        "channel": "positions",  
        "instId": "default"  
    },  
    "data": [  
        {  
            "posId": "1",  
            "instId": "ETHUSDT",  
            "marginCoin": "USDT",  
            "marginSize": "9.5",  
            "marginMode": "crossed",  
            "holdSide": "short",  
            "posMode": "hedge_mode",  
            "total": "0.1",  
            "available": "0.1",  
            "frozen": "0",  
            "openPriceAvg": "1900",  
            "leverage": 20,  
            "achievedProfits": "0",  
            "unrealizedPL": "0",  
            "unrealizedPLR": "0",  
            "liquidationPrice": "5788.108475905242",  
            "keepMarginRate": "0.005",  
            "marginRate": "0.004416374196",  
            "cTime": "1695649246169",  
            "breakEvenPrice": "24778.97",  
            "totalFee": "1.45",  
            "deductedFee": "0.388",  
            "markPrice": "2500",  
            "uTime": "1695711602568",              
            "assetMode": "union",  
            "autoMargin": "off"  
        }  
    ],  
    "ts": 1695717430441  
}
```

### Push Parameters[​](#push-parameters "Direct link to Push Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| action | String | 'snapshot' |
| arg | Object | Channels with successful subscription |
| > channel | String | Channel name: `positions` |
| > instType | String | Product type `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures |
| > instId | String | `default` |
| data | List<Object> | Subscription data |
| > posId | String | Position ID |
| > instId | String | Product ID, delivery contract reference：<https://www.bitget.com/api-doc/common/release-note> |
| > marginCoin | String | Currency of occupied margin |
| > marginSize | String | Occupied margin (amount) |
| > marginMode | String | Margin mode |
| > holdSide | String | Position direction |
| > posMode | String | Position mode |
| > total | String | Open position size |
| > available | String | Size of positions that can be closed |
| > frozen | String | Amount of frozen margin |
| > openPriceAvg | String | Average entry price |
| > leverage | String | Leverage |
| > achievedProfits | String | Realized PnL |
| > unrealizedPL | String | Unrealized PnL |
| > unrealizedPLR | String | Unrealized ROI |
| > liquidationPrice | String | Estimated liquidation price |
| > keepMarginRate | String | Maintenance margin rate |
| > isolatedMarginRate | String | Actual margin ratio under isolated margin mode |
| > marginRate | String | Occupancy rate of margin |
| > breakEvenPrice | String | Position breakeven price |
| > totalFee | String | Funding fee, the accumulated value of funding fee during the position,The initial value is empty, indicating that no funding fee has been charged yet. |
| > deductedFee | String | Deducted transaction fees: transaction fees deducted during the position |
| > markPrice | String | Mark Price |
| > assetMode | String | Account Mode  `union`: Union Margin   `single`: Single Margin |
| > cTime | String | Position creation time, milliseconds format of Unix timestamp, e.g.1597026383085 |
| > uTime | String | Lastest position update time, milliseconds format of Unix timestamp, e.g.1597026383085 |