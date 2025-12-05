# Get Order Details

### Description[​](#description "Direct link to Description")

Query order details using either orderId or clientOid.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/trade/order-info
* Rate limit: 20/sec/UID
* Permission: UTA trade (read)

Request

```json
curl "https://api.bitget.com/api/v3/trade/order-info?orderId=1233965375251996672" \  
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
| orderId | String | No | Order ID Either `clientOid` or `orderId` must be provided. If both are present or do not match, `orderId` will take priority |
| clientOid | String | No | Client order ID Either `clientOid` or `orderId` must be provided. If both are present or do not match, `orderId` will take priority |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1730369201783,  
  "data": {  
    "orderId": "111111111111111111",  
    "clientOid": "111111111111111111",  
    "category": "SPOT",  
    "symbol": "ETHUSDT",  
    "orderType": "market",  
    "side": "buy",  
    "price": "0",  
    "qty": "0",  
    "amount": "100",  
    "cumExecQty": "0.0372",  
    "cumExecValue": "99.853356",  
    "avgPrice": "2684.23",  
    "timeInForce": "gtc",  
    "orderStatus": "filled",  
    "posSide": "",  
    "holdMode": "",  
    "tradeSide": "open",  
    "reduceOnly": "NO",  
    "feeDetail": [  
      {  
        "feeCoin": "ETH",  
        "fee": "0.00000744"  
      }  
    ],  
    "cancelReason": "",  
    "execType": "",  
    "createdTime": "1730295766596",  
    "updatedTime": "1730295766691"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Return Field | Parameter Type | Description |
| --- | --- | --- |
| orderId | String | Order ID |
| clientOid | String | Client order ID |
| category | String | Product type  `SPOT` Spot trading   `MARGIN` Margin trading   `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures |
| symbol | String | Symbol name |
| price | String | Order price |
| qty | String | Order quantity *The unit is base coin* |
| amount | String | Order amount *The unit is quote coin* |
| orderType | String | Order type `limit`/`market` |
| cumExecQty | String | Cumulative executed quantity *The unit is base coin* |
| cumExecValue | String | Cumulative executed value *The unit is quote coin* |
| avgPrice | String | Average executed price |
| orderStatus | String | Order status `live` Order created.  `new` Order matching.  `partially_filled` Partially filled `filled` Fully filled `cancelled` Cancelled |
| side | String | Order side `buy`/`sell` |
| timeInForce | String | Time in force `ioc` Immediate or cancel `fok`: Fill or kill `gtc`: Good 'til canceled `post_only`: Post (Maker) only |
| posSide | String | Position side `long`/`short` |
| tradeSide | String | Trade side  `open`/`close`  Detailed enumerations can be obtained on the Enumeration page. |
| holdMode | String | Position mode `one_way_mode`/`hedge_mode` |
| stpMode | String | STP Mode(Self Trade Prevention)  `none`: not setting STP(default) `cancel_taker`: cancel taker order  `cancel_maker`: cancel maker order  `cancel_both`: cancel both of taker and maker orders |
| reduceOnly | String | Reduce-only identifier `YES`/`NO`  Available only for futures |
| feeDetail | Array | Fee detail |
| > feeCoin | String | Fee coin |
| > fee | String | Total fee |
| cancelReason | String | Cancel reason `normal_cancel`  Detailed enumerations can be obtained on the Enumeration page. |
| execType | String | Execution type `normal`Normal  `offset` Netting of hedged positions  `reduce` Forced reduction `liquidation` Liquidation `delivery` Delivery |
| createdTime | String | Created timestamp A Unix millisecond timestamp. |
| updatedTime | String | Updated timestamp A Unix millisecond timestamp. |