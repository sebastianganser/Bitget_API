# Get Fill History

### Description[​](#description "Direct link to Description")

Query historical fills within the last 90 days.

* **Query Range Constraint**  
   Each individual query can only cover a maximum of 30 days within the 90-day window.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/trade/fills
* Rate limit: 20/sec/UID
* Permission: UTA trade (read)

Request

```json
curl "https://api.bitget.com/api/v3/trade/fills?orderId=111111111111111111" \  
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
| category | String | No | Product type   `SPOT` Spot trading   `MARGIN` Margin trading   `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures |
| orderId | String | No | Order ID |
| startTime | String | No | Start timestamp  A Unix timestamp in milliseconds e.g.,`1597026383085` The access window is 90 days. |
| endTime | String | No | End timestamp  A Unix timestamp in milliseconds e.g.,`1597026383185`  The time range between `startTime` and `endTime` must not exceed 30 days. |
| limit | String | No | Limit per page  Default:`100`. Maximum:`100` |
| cursor | String | No | Cursor  Pagination is implemented by omitting the cursor in the first query and applying the cursor from the previous query for subsequent pages |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1750142995229,  
  "data": {  
    "list": [  
      {  
        "execId": "131111111111111111",  
        "execLinkId": "131111111111111111",  
        "orderId": "131111111111111111",  
        "clientOid": "131111111111111111",  
        "category": "USDT-FUTURES",  
        "symbol": "BTCUSDT",  
        "orderType": "market",  
        "side": "sell",  
        "execPrice": "106950.1",  
        "execQty": "0.01",  
        "execValue": "1069.501",  
        "tradeScope": "taker",  
        "tradeSide": "open",  
        "feeDetail": [  
          {  
            "feeCoin": "USDT",  
            "fee": "0.6417006"  
          }  
        ],  
        "createdTime": "1750141421721",  
        "updatedTime": "1750141421728",  
        "execPnl": "-0.002"  
      }  
    ],  
    "cursor": "131111111111111111"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| list | Array | Fill list |
| >execId | String | Fill ID |
| >execLinkId | String | Execution correlation ID |
| >orderId | String | Order ID |
| >clientOid | String | Client order ID |
| >category | String | Product type   `SPOT` Spot trading   `MARGIN` Margin trading   `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures |
| >symbol | String | Symbol name |
| >orderType | String | Order type  `limit`/`market` |
| >execPrice | String | Fill price |
| >execQty | String | Fill quantity *The unit is base coin* |
| >execValue | String | Fill value *The unit is quote coin* |
| >feeDetail | String | Fee detail |
| >>feeCoin | String | Fee coin |
| >>fee | String | Fee |
| >side | String | Fill side `buy`/`sell` |
| >tradeScope | String | Trade scope `taker`/`maker` |
| >tradeSide | String | Trade side  `open`/`close`  Detailed enumerations can be obtained on the Enumeration page. |
| >createdTime | String | Created timestamp A Unix millisecond timestamp. e.g.,`1736388000` |
| >updatedTime | String | Updated timestamp A Unix millisecond timestamp. e.g.,`1736388000` |
| >execPnl | String | Closed Position Profit and Loss |
| cursor | String | Cursor |