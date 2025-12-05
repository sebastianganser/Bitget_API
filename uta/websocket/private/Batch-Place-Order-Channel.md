# Batch Place Order Channel

### Description[​](#description "Direct link to Description")

* Maximum 20 orders allowed in a single request
* Please contact your BD or RM to apply for access permissions.

Request Example

```json
{  
    "op": "trade",  
    "id": "1750035029506",  
    "category": "spot",  
    "topic": "batch-place",  
    "args": [  
        {  
            "clientOid": "xxxxxxxx",  
            "orderType": "limit",  
            "price": "100",  
            "qty": "0.1",  
            "side": "buy",  
            "symbol": "BTCUSDT",  
            "timeInForce": "gtc"  
        },  
        {  
            "clientOid": "xxxxxxxx",  
            "orderType": "limit",  
            "price": "100",  
            "qty": "0.15",  
            "side": "buy",  
            "symbol": "BTCUSDT",  
            "timeInForce": "gtc"  
        }  
    ]  
}
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| op | String | Yes | Operation:   `trade` |
| id | String | Yes | Request identifier |
| topic | String | Yes | Topic:   `batch-place` |
| category | String | Yes | Category  `spot`Spot `margin` Margin  `usdt-futures` USDT futures `coin-futures` Coin futures `usdc-futures` USDC futures |
| args | List<Object> | Yes | Channel list |
| > symbol | String | Yes | Symbol name |
| > orderType | String | Yes | Order type  `limit` : Limit order  `market` : Market order |
| > qty | String | Yes | Order quantity - Spot  For market buy orders, the unit is quote coin  For limit and market sell orders, the unit is base coin  - Futures The unit is base coin |
| > price | String | Yes | Order price This field is required when orderType is `limit` |
| > side | String | Yes | Order side `buy` `sell` |
| > posSide | String | No | Position side `long`  `short`  This field is required in hedge-mode positions. Available only for futures |
| > timeInForce | String | No | Time in force   `gtc`: Good 'til canceled. It remains active until it is either filled or manually canceled. `ioc`: Immediate or cancel. It must be executed immediately, with any unfilled portion canceled. `fok`: Fill or kill. It must be fully executed immediately, or it is canceled entirely.   `post_only`: Post only. It will only be added to the order book as a maker.  This field is required when orderType is `limit`. If omitted, it defaults to `gtc` |
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
  "id": "1750035029506",  
  "category": "spot",  
  "topic": "batch-place",  
  "args": [  
    {  
      "code": "0",  
      "msg": "Success",  
      "symbol": "BTCUSDT",  
      "orderId": "xxxxxxxx",  
      "clientOid": "xxxxxxxx"  
    },  
    {  
      "code": "0",  
      "msg": "Success",  
      "symbol": "BTCUSDT",  
      "orderId": "xxxxxxxx",  
      "clientOid": "xxxxxxxx"  
    }  
  ],  
  "code": "0",  
  "msg": "Success",  
  "ts": "1750035029925"  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameters | Type | Description |
| --- | --- | --- |
| event | String | Event `trade`/`error` |
| id | String | Request identifier |
| topic | String | Topic:   `batch-place` |
| category | String | Category  `spot`Spot `margin` Margin  `usdt-futures` USDT futures `coin-futures` Coin futures `usdc-futures` USDC futures |
| args | List<Object> | Channel list |
| > symbol | String | Symbol name |
| > orderId | String | Order ID |
| > clientOid | String | Client order ID |
| > code | String | Code |
| > msg | String | Message |
| code | String | Code |
| msg | String | Message |
| ts | String | Timestamp |