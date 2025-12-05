# Place Order

### Description[​](#description "Direct link to Description")

This endpoint allows order placement across spot, margin, or futures markets with customizable parameters, including
price, quantity, and order type, etc.

* Futures  
  For one-way mode, reduce-only orders are allowed to place. If a reduce only order already exists and the order
  quantity equals the position size, or if a new reduce only order exceeds the remaining position size, the previous
  reduction order will be automatically canceled and replaced. In this case, the returned orderId will be null.
  It is recommended to always provide a clientOid.
* Margin  
  Margin orders will automatically trigger fund borrowing.
* Order Check
  + Futures:price must meet the price multiplier and be a multiple of priceMultiplier, and conform to the
    pricePrecision decimal places. qty must be greater than or equal to minOrderAmount and be a multiple of
    sizeMultiplier.
  + Spot:price must meet the decimal place requirement. qty must be greater than or equal to minOrderAmount.
* Open Position Logic
  + Hedge-mode  
    Open long: side=buy & posSide=long  
    Open Short: side=sell & posSide=short  
    Close long: side=sell & posSide=long  
    Close short: side=buy & posSide=short
  + One-way-mode  
    Open long: side=buy  
    Open short: side=sell  
    Close long: side=sell & reduceOnly=yes  
    Close short: side=buy & reduceOnly=yes
* Order Limit
  + Futures: 400 orders across all USDT, Coin-M, and USDC futures trading pairs.
  + Spot: 400 orders across all spot and margin trading pairs.
* ClientOid Constraints
  Please ensure your clientOid matches the regular expression `^[\.A-Z\:/a-z0-9_-]{1,32}$`, consisting of 1 to 32
  characters, including periods (.), uppercase letters, colons (:), lowercase letters, numbers, underscores (\_), and
  hyphens (-).
* Request Monitor   
  The API requests will be monitored. If the total number of orders for a single account (including master and
  sub-accounts) exceeds a set daily limit (UTC 00:00 - UTC 24:00), the platform reserves the right to issue reminders,
  warnings, and enforce necessary restrictions. By using the API, clients acknowledge and agree to comply with these
  terms.
* Error Sample { "code":"40762", "msg":"The order size is greater than the max open size", "requestTime":1627293504612 } This error code may occur in the following scenarios.
  + Insufficient account balance.
  + The position tier for this symbol has reached its limit. [Position tiers](https://www.bitget.com/trade-info/position-gear?symbolId=BTCUSDT_UMCBL)
* Note: If the following errors occur when placing an order, please use clientOid to query the order details to confirm
  the final result of the operation.

> { "code": "40010", "msg": "Request timed out", "id": 1666268894074, "event":"error" }  
> { "code": "40725", "msg": "service return an error", "id": 1666268894071, "event":"error" }  
> { "code": "45001", "msg": "Unknown error", "id": 1666268894071, "event":"error" }

Request Example

```json
{  
  "op": "trade",  
  "id": "1750034396082",  
  "category": "spot",  
  "topic": "place-order",  
  "args": [  
    {  
      "orderType": "limit",  
      "price": "100",  
      "qty": "0.1",  
      "side": "buy",  
      "symbol": "BTCUSDT",  
      "timeInForce": "gtc",  
    }  
  ]  
}
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| op | String | Yes | Operation:   `trade` |
| id | String | Yes | Request identifier |
| topic | String | Yes | Topic:   `place-order` |
| category | String | Yes | Category  `spot`Spot `margin` Margin  `usdt-futures` USDT futures `coin-futures` Coin futures `usdc-futures` USDC futures |
| apiCode | String | No | API rebate identifier |
| args | List<Object> | Yes | Channel list |
| > symbol | String | Yes | Symbol name |
| > orderType | String | Yes | Order type  `limit` : Limit order  `market` : Market order |
| > qty | String | Yes | Order quantity - Spot  For market buy orders, the unit is quote coin  For limit and market sell orders, the unit is base coin  - Futures The unit is base coin |
| > price | String | Yes | Order price This field is required when orderType is `limit` |
| > side | String | Yes | Order side `buy` `sell` |
| > posSide | String | No | Position side `long`  `short`  This field is required in hedge-mode positions. Available only for futures |
| > timeInForce | String | No | Time in force   `gtc`: Good 'til canceled. It remains active until it is either filled or manually canceled. `ioc`: Immediate or cancel. It must be executed immediately, with any unfilled portion canceled. `fok`: Fill or kill. It must be fully executed immediately, or it is canceled entirely.   `post_only`: Post only. It will only be added to the order book as a maker.  This field is required when orderType is `limit`. If omitted, it defaults to `gtc` |
| > reduceOnly | String | No | Reduce-only identifier `YES`/`NO` default`NO`; `YES` indicates that your position may only be reduced in size upon the activation of this order |
| > clientOid | String | No | Client order ID |
| > stpMode | String | No | STP Mode(Self Trade Prevention) `none`： no STP settings(Default) `cancel_taker`：cancel taker order  `cancel_maker`：cancel maker order  `cancel_both`：cancel both of taker and maker orders |
| > tpTriggerBy | String | No | Preset Take-Profit Trigger Type `market`Market Price `mark` Mark Price If not specified, the default value is market price   Note: This field is only valid for the contract business lines: USDT-Futures, COIN-Futures, and USDC-Futures. |
| > slTriggerBy | String | No | Preset Stop-Loss Trigger Type `market`Market Price `mark` Mark Price If not specified, the default value is market price   Note: This field is only valid for the contract business lines: USDT-Futures, COIN-Futures, and USDC-Futures. |
| > takeprofit | String | No | Preset Take-Profit Trigger Price |
| > stoploss | String | No | Preset Stop-Loss Trigger Price |
| > tpOrderType | String | No | Take-Profit Trigger Strategy Order Type `limit` Limit Order `market` Market Order |
| > slOrderType | String | No | Stop-Loss Trigger Strategy Order Type `limit` Limit Order `market` Market Order |
| > tpLimitPrice | String | No | Take-Profit Strategy Order Execution Price This field is only valid for limit orders (when `tpOrderType=limit`); it is ignored for market orders. |
| > slLimitPrice | String | No | Stop-Loss Strategy Order Execution Price This field is only valid for limit orders (when `slOrderType=limit`); it is ignored for market orders. |

Response

```json
{  
  "event": "trade",  
  "id": "1750034396082",  
  "category": "spot",  
  "topic": "place-order",  
  "args": [  
    {  
      "symbol": "BTCUSDT",  
      "orderId": "xxxxxxxx",  
      "clientOid": "xxxxxxxx",  
      "cTime": "1750034397008"  
    }  
  ],  
  "code": "0",  
  "msg": "success",  
  "ts": "1750034397076"  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameters | Type | Description |
| --- | --- | --- |
| event | String | Event `trade`/`error` |
| id | String | Request identifier |
| topic | String | Topic `place-order` |
| category | String | Category  `spot`Spot `margin` Margin  `usdt-futures` USDT futures `coin-futures` Coin futures `usdc-futures` USDC futures |
| args | List<Object> | Channel list |
| > cTime | String | Order creation time  Unix millisecond timestamp |
| > symbol | String | Symbol name |
| > orderId | String | Order ID |
| > clientOid | String | Client order ID |
| code | String | Code |
| msg | String | Message |
| ts | String | Timestamp |