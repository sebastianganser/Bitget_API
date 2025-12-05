# Fill Channel

Data will be pushed when order filled.

### Description[​](#description "Direct link to Description")

Trade details channel

Data will be pushed when order filled.

Request Example

```json
{  
    "op": "subscribe",  
    "args": [  
        {  
            "instType": "USDT-FUTURES",  
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
| args | List<Object> | Yes | List of channels to request subscription |
| > channel | String | Yes | Channel name: `fill` |
| > instType | String | Yes | Product type `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures |
| > instId | String | No | Product ID or default， delivery contract reference：<https://www.bitget.com/api-doc/common/release-note#optimization-of-delivery-futures> |

Response Example

```json
{  
    "event": "subscribe",  
    "arg": {  
        "instType": "USDT-FUTURES",  
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
| > channel | String | Channel name: `fill` |
| > instType | String | Product type `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures |
| > instId | String | Product ID or default delivery contract reference：<https://www.bitget.com/api-doc/common/release-note#optimization-of-delivery-futures> |
| code | String | Error code |
| msg | String | Error message |

Push Data

```json
{  
    "action":"snapshot",  
    "arg":{  
        "instType":"USDT-FUTURES",  
        "channel":"fill",  
        "instId":"default"  
    },  
    "data":[  
        {  
            "orderId":"111",  
            "clientOid":"111",  
            "tradeId":"222",  
            "symbol":"BTCUSDT",  
            "side":"buy",  
            "orderType":"market",  
            "posMode":"one_way_mode",  
            "price":"51000.5",  
            "baseVolume":"0.01",  
            "quoteVolume":"510.005",  
            "profit":"0",  
            "tradeSide":"open",  
            "tradeScope":"taker",  
            "feeDetail":[  
                {  
                    "feeCoin":"USDT",  
                    "deduction":"no",  
                    "totalDeductionFee":"0",  
                    "totalFee":"-0.183717"  
                }  
            ],  
            "cTime":"1703577336606",  
            "uTime":"1703577336606"  
        }  
    ],  
    "ts":1703577336700  
}
```

### Push Parameters[​](#push-parameters "Direct link to Push Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| action | String | `snapshot` |
| arg | Object | Channels with successful subscription |
| > channel | String | Channel name: `fill` |
| > instType | String | Product type `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures |
| > instId | String | Product ID or default delivery contract reference：<https://www.bitget.com/api-doc/common/release-note#optimization-of-delivery-futures> |
| data | List<Object> | Subscription data |
| > orderId | String | Order ID |
| > clientOid | String | Customize order ID |
| > tradeId | String | Trade ID |
| > symbol | String | Symbol Name |
| > side | String | Trade direction `buy`: Buy  `sell`: Sell Please note, for this channel, in hedge position mode, **Open Long** and **Close Short**, the "side" will be `buy`; **Close Long** and **Open Short**, the "side" will be `sell` |
| > orderType | String | Order type `limit`  limit order `market` market order |
| > posMode | String | Hold Mode `one_way_mode`  `hedge_mode` |
| > price | String | Order price |
| > baseVolume | String | Amount of base coin |
| > quoteVolume | String | Amount of denomination coin |
| > profit | String | Realized PnL |
| > tradeSide | String | Trade type `close`: Close (open and close mode) `open`: Open (open and close mode) `reduce_close_long`: Liquidate partial long positions for hedge position mode `reduce_close_short`：Liquidate partial short positions for hedge position mode `burst_close_long`：Liquidate long positions for hedge position mode `burst_close_short`：Liquidate short positions for hedge position mode `offset_close_long`：Liquidate partial long positions for netting for hedge position mode `offset_close_short`：Liquidate partial short positions for netting for hedge position mode `delivery_close_long`：Delivery long positions for hedge position mode `delivery_close_short`：Delivery short positions for hedge position mode `dte_sys_adl_close_long`：ADL close long position for hedge position mode `dte_sys_adl_close_short`：ADL close short position for hedge position mode `buy_single`：Buy, one way postion mode `sell_single`：Sell, one way postion mode `reduce_buy_single`：Liquidate partial positions, buy, one way position mode `reduce_sell_single`：Liquidate partial positions, sell, one way position mode `burst_buy_single`：Liquidate short positions, buy, one way postion mode `burst_sell_single`：Liquidate partial positions, sell, one way position mode `delivery_sell_single`：Delivery sell, one way position mode `delivery_buy_single`：Delivery buy, one way position mode `dte_sys_adl_buy_in_single_side_mode`：ADL close position, buy, one way position mode `dte_sys_adl_sell_in_single_side_mode`：ADL close position, sell, one way position mode |
| > tradeScope | String | The liquidity direction `taker`   `maker` |
| > feeDetail | List<Object> | Transaction fee of the order |
| >> deduction | String | deduction `yes`  `no` |
| >> totalDeductionFee | String | Fee of deduction |
| >> totalFee | String | Fee of all |
| >> feeCoin | String | Currency of transaction fee |
| > cTime | String | Create Time，milliseconds format of Unix timestamp, e.g.1597026383085 |
| > uTime | String | Update Time，milliseconds format of Unix timestamp, e.g.1597026383085 |