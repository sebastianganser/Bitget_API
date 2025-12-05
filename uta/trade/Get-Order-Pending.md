# Get Open Orders

### Description[​](#description "Direct link to Description")

Query unfilled or partially filled orders. To query closed orders, please use the order history endpoint.

* **Order Limit**
  + **Futures**: 400 orders across all USDT, Coin-M, and USDC futures trading pairs.
  + **Spot**: 400 orders across all spot and margin trading pairs.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/trade/unfilled-orders
* Rate limit: 20/sec/UID
* Permission: UTA trade (read)

Request

```json
curl "https://api.bitget.com/api/v3/trade/unfilled-orders?category=USDT-FUTURES&symbol=BTCUSDT" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*" \  
  -H "ACCESS-PASSPHRASE:*" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:zh-CN" \  
  -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameters | Type | Required | Description |
| --- | --- | --- | --- |
| category | String | No | Product type   `SPOT` Spot trading   `MARGIN` Margin trading   `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures |
| symbol | String | No | Symbol name  e.g.,`BTCUSDT` |
| startTime | String | No | Start timestamp  A Unix timestamp in milliseconds e.g.,`1597026383085` |
| endTime | String | No | End timestamp  A Unix timestamp in milliseconds e.g.,`1597026383085` |
| limit | String | No | Limit per page Default:`100`. Maximum:`100` |
| cursor | String | No | Cursor  Pagination is implemented by omitting the cursor in the first query and applying the cursor from the previous query for subsequent pages |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1730186730084,  
  "data": {  
    "list": [  
      {  
        "orderId": "111111111111111111",  
        "clientOid": "111111111111111111",  
        "category": "USDT-FUTURES",  
        "symbol": "BTCUSDT",  
        "orderType": "limit",  
        "side": "buy",  
        "price": "45000",  
        "qty": "0.01",  
        "amount": "0",  
        "cumExecQty": "0",  
        "cumExecValue": "0",  
        "avgPrice": "0",  
        "timeInForce": "gtc",  
        "orderStatus": "live",  
        "posSide": "long",  
        "holdMode": "hedge_mode",  
        "reduceOnly": "NO",  
        "feeDetail": [  
          {  
            "feeCoin": null,  
            "fee": null  
          }  
        ],  
        "createdTime": "1730186725663",  
        "updatedTime": "1730186725691"  
      }  
    ],  
    "cursor": "1235058132196622336"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameters | Type | Description |
| --- | --- | --- |
| list | Array | Order list |
| >orderId | String | Order ID |
| >clientOid | String | Client order ID |
| >category | String | Business Line `SPOT`: Spot trading `MARGIN`: Margin trading `USDT-FUTURES`: USDT futures `COIN-FUTURES`: Coin-M futures  `USDC-FUTURES`: USDC futures |
| >symbol | String | Symbol name e.g.,`BTCUSDT` |
| >price | String | Order price |
| >qty | String | Order quantity  *The unit is base coin* |
| >amount | String | Order amount  *The unit is quote coin*   Applicable to Spot and Margin. |
| >orderType | String | Order type `limit`/`market` |
| >cumExecQty | String | Cumulative executed order quantity  *The unit is base coin* |
| >cumExecValue | String | Cumulative executed order value  *The unit is quote coin* |
| >avgPrice | String | Average price |
| >orderStatus | String | Order status `live` Order created.  `new` Order matching.  `partially_filled` Partially filled |
| >side | String | Order side `buy`/`sell` |
| >timeInForce | String | Time in force `ioc` Immediate or cancel. It must be executed immediately, with any unfilled portion canceled.  `fok` Fill or kill. It must be fully executed immediately, or it is canceled entirely.  `gtc` Good 'til canceled. It remains active until it is either filled or manually canceled. `post_only` Post only. It will only be added to the order book as a maker. |
| >posSide | String | Position side `long`/`short` |
| >holdMode | String | Holding mode `one_way_mode`/`hedge_mode` |
| >stpMode | String | STP Mode(Self Trade Prevention)  `none`: not setting STP(default) `cancel_taker`: cancel taker order  `cancel_maker`: cancel maker order  `cancel_both`: cancel both of taker and maker orders |
| >reduceOnly | String | Reduce-only identifier  `YES`/`NO` |
| >feeDetail | Array | Fee detail list |
| >> feeCoin | String | Fee coin |
| >> fee | String | Total fee |
| >createdTime | String | Order created timestamp A Unix millisecond timestamp |
| >updatedTime | String | Order update timestamp A Unix millisecond timestamp |