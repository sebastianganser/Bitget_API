# Place Order

### Description[​](#description "Direct link to Description")

This endpoint allows the order placement across spot, margin, or futures markets with customizable parameters, including price, quantity, and order type, etc.

* **Upcoming Features** (currently not supported)

  + Isolated spot margin will be available soon.
  + Copy trading order placement will be available soon.
* **Futures**   
  For one-way mode, reduce-only orders are allowed to place. If a reduce only order already exists and the order quantity equals the position size, or if a new reduce only order exceeds the remaining position size, the previous reduction order will be automatically canceled and replaced. In this case, the returned orderId will be null.   
  **It is recommended to always provide a `clientOid`.**

* **Margin**   
  Margin orders will automatically trigger fund borrowing.

* **Order Check**

  + **Futures**:`price` must meet the price multiplier and be a multiple of `priceMultiplier`, and conform to the `pricePrecision` decimal places. `qty` must be greater than or equal to `minOrderAmount` and be a multiple of `sizeMultiplier`.
  + **Spot**:`price` must meet the decimal place requirement. `qty` must be greater than or equal to `minOrderAmount`.

* **Open Position Logic**

  + **Hedge-mode**  
    Open long: `side=buy` & `posSide=long`  
    Open Short: `side=sell` & `posSide=short`  
    Close long: `side=sell` & `posSide=long`  
    Close short: `side=buy` & `posSide=short`
  + **One-way-mode**  
    Open long: `side=buy`  
    Open short: `side=sell`  
    Close long: `side=sell` & `reduceOnly=yes`  
    Close short: `side=buy` & `reduceOnly=yes`

* **Order Limit**
  + **Futures**: 400 orders across all USDT, Coin-M, and USDC futures trading pairs.
  + **Spot**: 400 orders across all spot and margin trading pairs.

* **ClientOid Constraints**  
  Please ensure your clientOid matches the regular expression `^[\.A-Z\:/a-z0-9_-]{1,32}$`, consisting of 1 to 32 characters, including periods (.), uppercase letters, colons (:), lowercase letters, numbers, underscores (\_), and hyphens (-).

* **Request Monitor**  
  The API requests will be monitored. If the total number of orders for a single account (including master and sub-accounts) exceeds a set daily limit (UTC 00:00 - UTC 24:00), the platform reserves the right to issue reminders, warnings, and enforce necessary restrictions. By using the API, clients acknowledge and agree to comply with these terms.

* **API Broker rebate identifier**:  
  The following code block needs to be added to the HTTP Header of the request.

  > "X-CHANNEL-API-CODE":"your-channel-api-code"
* **Error Sample**

  > { "code":"40762", "msg":"The order size is greater than the max open size", "requestTime":1627293504612 }
  >
  > This error code may occur in the following scenarios.
  >
  > + Insufficient account balance.
  > + The position tier for this symbol has reached its limit. For details on specific tiers, please refer [here](https://www.bitget.com/futures/introduction/position-tier?code=BTCUSDT_UMCBL?business=USDT_MIX_CONTRACT_BL) .

Note: If the following errors occur when placing an order, please use `clientOid` to query the order details to confirm the final result of the operation.

> { "code": "40010", "msg": "Request timed out", "requestTime": 1666268894074, "data": null }  
> { "code": "40725", "msg": "service return an error", "requestTime": 1666268894071, "data": null }  
> { "code": "45001", "msg": "Unknown error", "requestTime": 1666268894071, "data": null }

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v3/trade/place-order
* Rate limit: 10/sec/UID
* Permission: UTA trade (read & write)

Request

```json
curl -X POST "https://api.bitget.com/api/v3/trade/place-order" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*" \  
  -H "ACCESS-PASSPHRASE:*" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:zh-CN" \  
  -H "Content-Type: application/json" \  
  -d '{"category":"SPOT","symbol":"BGBUSDT","orderType":"limit","qty":"123","price":"1.11","side":"buy","posSide":"long","timeInForce":"gtc","reduceOnly":"no"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| category | String | Yes | Product type   `SPOT` Spot trading   `MARGIN` Margin trading   `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures |
| symbol | String | Yes | Symbol name  e.g.,`BTCUSDT` |
| qty | String | Yes | Order quantity  `Spot/Margin`  For market buy orders,the unit is **quote coin** For limit and market sell orders, the unit is **base coin**  `Futures`   The unit is **base coin** |
| price | String | No | Order price  This field is required when orderType is `limit` |
| side | String | Yes | Order side `buy`/`sell` |
| orderType | String | Yes | Order type `limit`/`market` |
| timeInForce | String | No | Time in force `ioc` Immediate or cancel. It must be executed immediately, with any unfilled portion canceled.  `fok` Fill or kill. It must be fully executed immediately, or it is canceled entirely.  `gtc` Good 'til canceled. It remains active until it is either filled or manually canceled. `post_only` Post only. It will only be added to the order book as a maker. This field is required when orderType is `limit`. If omitted, it defaults to `gtc` |
| posSide | String | No | Position side `long`/`short` This field is required in hedge-mode position.  Available only for futures |
| clientOid | String | No | Client order ID |
| reduceOnly | String | No | Reduce-only identifier `yes`/`no`, default `no`;  `yes` indicates that your position may only be reduced in size upon the activation of this order |
| stpMode | String | No | STP Mode(Self Trade Prevention)  `none`: not setting STP(default) `cancel_taker`: cancel taker order  `cancel_maker`: cancel maker order  `cancel_both`: cancel both of taker and maker orders |
| tpTriggerBy | String | No | Preset Take-Profit Trigger Type `market`: Market Price `mark`: Mark Price If not specified, the default value is market price Note: This field is only valid for the contract business lines: USDT-Futures, COIN-Futures, and USDC-Futures. |
| slTriggerBy | String | No | Preset Stop-Loss Trigger Type `market`: Market Price `mark`: Mark Price If not filled in, the default value is market price Note: This field is only valid for the contract business lines: USDT-Futures, COIN-Futures, and USDC-Futures |
| takeProfit | String | No | Preset Take-Profit Trigger Price |
| stopLoss | String | No | Preset Stop-Loss Trigger Price |
| tpOrderType | String | No | Take-Profit Trigger Strategy Order Type `limit`: Limit Order `market`: Market Order |
| slOrderType | String | No | Stop-Loss Trigger Strategy Order Type `limit`: Limit Order `market`: Market Order |
| tpLimitPrice | String | No | Take-Profit Strategy Order Execution Price This field is only valid for limit orders (when `tpOrderType=limit`); it is ignored for market orders. |
| slLimitPrice | String | No | Stop-Loss Strategy Order Execution Price This field is only valid for limit orders (when `slOrderType=limit`); it is ignored for market orders. |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1695806875837,  
  "data": {  
    "clientOid": "121211212122",  
    "orderId": "121211212122"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| orderId | String | Order ID |
| clientOid | String | Client order ID |