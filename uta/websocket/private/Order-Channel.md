# Order

### Description[​](#description "Direct link to Description")

The following events will trigger a data push:

1. No Push on first-time subscription
2. Push when spot/margin/futures orders are placed in the unified trading account
3. Push when spot/margin/futures orders are filled in the unified trading account
4. Push when spot/margin/futures orders are cancelled in the unified trading account

Request Example

```json
{  
    "op": "subscribe",  
    "args": [  
        {  
            "instType": "UTA",  
            "topic": "order"  
        }  
    ]  
}
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| op | String | Operation   `subscribe`/`unsubscribe` |
| args | List<Object> | Subscribed channel |
| > instType | String | Product type   `UTA` Unified trading account |
| > topic | String | Topic  `order` Order |

Response Example

```json
{  
  "event": "subscribe",  
  "arg": {  
    "instType": "UTA",  
    "topic": "order"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameters | Type | Description |
| --- | --- | --- |
| event | String | Operation   `subscribe` Subscribe   `unsubscribe` Unsubscribe   `error` Parameter error |
| arg | Object | Subscribed channel |
| > instType | String | Product type   `UTA` Unified Account |
| > topic | String | Topic   `order` Order channel |
| code | String | Error code |
| msg | String | Error message |

Push

```json
{  
  "action": "snapshot",  
  "arg": {  
    "instType": "UTA",  
    "topic": "order"  
  },  
  "data": [  
    {  
      "category": "usdt-futures",  
      "symbol": "BTCUSDT",  
      "orderId": "xxx",  
      "clientOid": "xxx",  
      "price": "",  
      "qty": "0.001",  
      "amount": "1000",  
      "holdMode": "hedge_mode",  
      "holdSide": "long",  
      "tradeSide": "open",  
      "orderType": "market",  
      "timeInForce": "gtc",  
      "side": "buy",  
      "marginMode": "crossed",  
      "marginCoin": "USDT",  
      "reduceOnly": "no",  
      "cumExecQty": "0.001",  
      "cumExecValue": "83.1315",  
      "avgPrice": "83131.5",  
      "totalProfit": "0",  
      "orderStatus": "filled",  
      "cancelReason": "",  
      "leverage": "20",  
      "feeDetail": [  
        {  
          "feeCoin": "USDT",  
          "fee": "0.0332526"  
        }  
      ],  
      "createdTime": "1742367838101",  
      "updatedTime": "1742367838115",  
      "stpMode": "none"  
    }  
  ],  
  "ts": 1742367838124  
}
```

### Push Parameters[​](#push-parameters "Direct link to Push Parameters")

| Parameters | Type | Description |
| --- | --- | --- |
| arg | Object | Subscribed channel |
| > instType | String | Product type `UTA` |
| > topic | String | Topic `order` |
| action | String | Push data action `snapshot` Full data |
| data | List<String> | Subscribed data |
| > category | String | Business line  `SPOT` Spot trading `MARGIN` Margin trading  `USDT-FUTURES` USDT Futures `COIN-FUTURES` Coin-M futures `USDC-FUTURES` USDC Futures |
| > orderId | String | Order ID |
| > clientOid | String | Client order ID |
| > price | String | Order price |
| > qty | String | Order quantity |
| > amount | String | Order amount |
| > holdMode | String | Holding mode `one_way_mode` This mode allows holding positions in a single direction, either long or short, but not both at the same time  `hedge_mode` This mode allows holding both long and short positions simultaneously |
| > tradeSide | String | Trade side  `open`/`close`  Detailed enumerations can be obtained on the Enumeration page. |
| > orderType | String | Order type  `limit`/`market` |
| > timelnForce | String | Time in force   `ioc`: Immediate or cancel `fok`: Fill or kill  `gtc`: Good 'till cancelled  `post_only`: Post (maker) only |
| > side | String | Order side   `buy`/`sell` |
| > holdSide | String | Position side   `long` Long position `short` Short position  `net` Net position |
| > marginMode | String | Margin mode  `crossed` Cross margin   `isolated` Isolated margin |
| > reduceOnly | String | Reduce-only identifier `yes`/`no` |
| > marginCoin | String | Margin coin |
| > cumExecQty | String | Cumulative executed quantity |
| > cumExecValue | String | Cumulative executed value |
| > avgPrice | String | Average execution price  If not executed, this field will default to 0 |
| > totalProfit | String | Total profit |
| > orderStatus | String | Order status `live` Order created.  `new` Order matching.  `partially_filled` Partially filled `filled` Fully filled `cancelled` Cancelled |
| > cancelReason | String | Reason for order cancellation |
| > leverage | String | Leverage |
| > feeDetail | List | Fee detail list |
| >> feeCoin | String | Fee coin |
| >> fee | String | Fee amount |
| > createdTime | String | Created time A Unix timestamp in milliseconds. e.g.,`1597026383085` |
| > updatedTime | String | Updated time A Unix timestamp in milliseconds. e.g.,`1597026383085` |
| > stpMode | String | STP Mode(Self Trade Prevention)  `none`: no STP settings `cancel_taker`: cancel taker order  `cancel_maker`: cancel maker order  `cancel_both`: cancel both of taker and maker orders |