# Get Order History

### Description[​](#description "Direct link to Description")

Query historical orders within the last 90 days.

* **Query Range Constraint**  
   Each individual query can only cover a maximum of 30 days within the 90-day window.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/trade/history-orders
* Rate limit: 20/sec/UID
* Permission: UTA trade (read)

Request

```json
curl "https://api.bitget.com/api/v3/trade/history-orders?category=USDT-FUTURES" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*" \  
  -H "ACCESS-PASSPHRASE:*" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:zh-CN" \  
  -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| category | String | Yes | Product type   `SPOT` Spot trading   `MARGIN` Margin trading   `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures |
| symbol | String | No | Symbol name  e.g.,`BTCUSDT` |
| startTime | String | No | Start timestamp  A Unix timestamp in milliseconds e.g.,`1597026383085` The access window is 90 days |
| endTime | String | No | End timestamp  A Unix timestamp in milliseconds e.g.,`1597026383185`  The time range between `startTime` and `endTime` must not exceed 30 days |
| limit | String | No | Limit per page  Default:`100`. Maximum:`100` |
| cursor | String | No | Cursor  Pagination is implemented by omitting the cursor in the first query and applying the cursor from the previous query for subsequent pages |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1730186348272,  
  "data": {  
    "list": [  
      {  
        "orderId": "111111111111111111",  
        "clientOid": "111111111111111111",  
        "category": "USDT-FUTURES",  
        "symbol": "BTCUSDT",  
        "orderType": "limit",  
        "side": "sell",  
        "price": "49534.4",  
        "qty": "0.429",  
        "amount": "0",  
        "cumExecQty": "0.429",  
        "cumExecValue": "21250.2929",  
        "avgPrice": "49534.4",  
        "timeInForce": "gtc",  
        "orderStatus": "filled",  
        "posSide": "long",  
        "holdMode": "hedge_mode",  
        "reduceOnly": "NO",  
        "feeDetail": [  
          {  
            "feeCoin": "USDT",  
            "fee": "4.2500586"  
          }  
        ],  
        "cancelReason": "normal_cancel",  
        "execType": "liquidation",  
        "createdTime": "1730181468493",  
        "updatedTime": "1730181468493"  
      }  
    ],  
    "cursor": "1233319323918499840"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| list | Array | Order list |
| >orderId | String | Order ID |
| >clientOid | String | Client order id |
| >category | String | Product Type   `SPOT` Spot trading   `MARGIN` Margin trading   `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures |
| >symbol | String | Symbol name  e.g.,`BTCUSDT` |
| >price | String | Order price |
| >qty | String | Order quantity  *The unit is base coin* |
| >amount | String | Order amount  *The unit is quote coin*   Applicable to Spot and Margin. |
| >orderType | String | Order type  `limit`/`market` |
| >cumExecQty | String | Cumulative executed order quantity  *The unit is base coin* |
| >cumExecValue | String | Cumulative executed order value  *The unit is quote coin* |
| >avgPrice | String | Average price |
| >orderStatus | String | Order status `live` Order created.  `new` Order matching.  `partially_filled` Partially filled `filled` Fully filled `cancelled` Cancelled |
| >side | String | Order side `buy`/`sell` |
| >timeInForce | String | Time in force `ioc` Immediate or cancel. It must be executed immediately, with any unfilled portion canceled.  `fok` Fill or kill. It must be fully executed immediately, or it is canceled entirely.  `gtc` Good 'til canceled. It remains active until it is either filled or manually canceled. `post_only` Post only. It will only be added to the order book as a maker. This field is required when orderType is `limit`. If omitted, it defaults to `gtc` |
| >posSide | String | Position side `long`/`short` |
| >holdMode | String | Holding mode `one_way_mode`/`hedge_mode` |
| >reduceOnly | String | Reduce-only identifier `yes`/`no`  `yes` indicates that your position may only be reduced in size upon the activation of this order |
| >feeDetail | Array | Fee detail |
| >>feeCoin | String | Fee coin |
| >>fee | String | Fee |
| >cancelReason | String | Cancel reason `normal_cancel` |
| >execType | String | Execution type `normal` Normal `offset` Offset  `reduce` Forced reduction   `liquidation` Liquidation `delivery` Delivery |
| >stpMode | String | STP Mode(Self Trade Prevention)  `none`: not setting STP(default) `cancel_taker`: cancel taker order  `cancel_maker`: cancel maker order  `cancel_both`: cancel both of taker and maker orders |
| >createdTime | String | Created timestamp A Unix millisecond timestamp. e.g.,`1736388000` |
| >updatedTime | String | Updated timestamp A Unix millisecond timestamp. e.g.,`1736388000` |
| cursor | String | Cursor |