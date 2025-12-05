# Place Strategy Order

### Description[​](#description "Direct link to Description")

Place a strategy order

* **API Broker rebate identifier**:  
  The following code block needs to be added to the HTTP Header of the request.
  > "X-CHANNEL-API-CODE":"your-channel-api-code"

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v3/trade/place-strategy-order
* Speed limit is 10 times/s (UID)
* Permission: UTA trade (read & write)

Request

```json
curl -X POST "https://api.bitget.com/api/v3/trade/place-strategy-order" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*" \  
  -H "ACCESS-PASSPHRASE:*" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:zh-CN" \  
  -H "Content-Type: application/json" \  
  -d '{ "category": "usdt-futures","symbol": "BTCUSDT","posSide": "long","stopLoss": "99000","takeProfit": "100800","clientOid": "121211212122"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| category | String | Yes | Product type   `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures |
| symbol | String | Yes | Symbol name  e.g.,`BTCUSDT` |
| clientOid | String | No | Client order ID  The idempotent validity period is six hours (not fully guaranteed) |
| type | String | No | Strategy Type `tpsl`Take-Profit and Stop-Loss Default:`tpsl` |
| tpslMode | String | No | Take-Profit and Stop-Loss Mode `full`All Positions Take-Profit and Stop-Loss `partial`Partial Position Take-Profit and Stop-Loss If left blank, the default value is `full` |
| qty | String | Yes | Order Quantity This is a required field when `tpslMode=partial`, and the unit is in the `base coin` |
| posSide | String | Yes | Position side `long`/`short` |
| tpTriggerBy | String | No | Take-Profit Trigger Type `market`: Market Price `mark`: Mark Price If not specified, the default value is market price |
| slTriggerBy | String | No | Stop-Loss Trigger Type `market`: Market Price `mark`: Mark Price If not filled in, the default value is market price |
| takeProfit | String | No | Take-Profit Trigger Price |
| stopLoss | String | No | Stop-Loss Trigger Price |
| tpOrderType | String | No | Take-Profit Trigger Strategy Order Type `limit`: Limit Order `market`: Market Order If not filled in, the default value is market price |
| slOrderType | String | No | Stop-Loss Trigger Strategy Order Type `limit`: Limit Order `market`: Market Order If not filled in, the default value is market price |
| tpLimitPrice | String | No | Take-Profit Strategy Order Execution Price This field is only valid for limit orders (when `tpOrderType=limit`); it is ignored for market orders. |
| slLimitPrice | String | No | Stop-Loss Strategy Order Execution Price This field is only valid for limit orders (when `slOrderType=limit`); it is ignored for market orders |

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