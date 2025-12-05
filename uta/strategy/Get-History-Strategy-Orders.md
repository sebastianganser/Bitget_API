# History Strategy Orders

### Description[​](#description "Direct link to Description")

Get historical strategy orders

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/trade/history-strategy-orders
* Speed limit is 20 times/s (UID)
* Permission: UTA trade (read)

Request

```json
curl "https://api.bitget.com/api/v3/trade/history-strategy-orders?category=usdt-futures&type=tpsl" \  
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
| category | String | Yes | Product type   `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures |
| type | String | No | Strategy Type `tpsl`Take-Profit and Stop-Loss |
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
        "qty": "0.01",  
        "posSide": "long",  
        "tpTriggerBy": "market",  
        "slTriggerBy": "market",  
        "takeProfit": "110000",  
        "stopLoss": "90000",  
        "tpOrderType": "market",  
        "slOrderType": "market",  
        "tpLimitPrice": "91000",  
        "slLimitPrice": "111000",  
        "createdTime": "1730186725663",  
        "updatedTime": "1730186725691"  
      }  
    ]  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| list | Array | Order list |
| >orderId | String | Order ID |
| >clientOid | String | Client order ID |
| >category | String | Product type   `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures |
| >symbol | String | Symbol name  e.g.,`BTCUSDT` |
| >qty | String | Order Quantity |
| >posSide | String | Position side `long`/`short` |
| >triggerType | String | Trigger Type `takeProfit`Take-Profit `stopLoss`Stop-Loss |
| >tpTriggerBy | String | Take-Profit Trigger Type `market`: Market Price `mark`: Mark Price |
| >slTriggerBy | String | Stop-Loss Trigger Type `market`: Market Price `mark`: Mark Price |
| >takeProfit | String | Take-Profit Trigger Price |
| >stopLoss | String | Stop-Loss Trigger Price |
| >tpOrderType | String | Take-Profit Trigger Strategy Order Type `limit`: Limit Order `market`: Market Order |
| >slOrderType | String | Stop-Loss Trigger Strategy Order Type `limit`: Limit Order `market`: Market Order |
| >tpLimitPrice | String | Take-Profit Strategy Order Execution Price |
| >slLimitPrice | String | Stop-Loss Strategy Order Execution Price |
| >createdTime | String | Order created timestamp A Unix millisecond timestamp |
| >updatedTime | String | Order update timestamp A Unix millisecond timestamp |