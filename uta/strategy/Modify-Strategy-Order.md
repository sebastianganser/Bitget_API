# Modify Strategy Order

### Description[​](#description "Direct link to Description")

Modify strategy order

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v3/trade/modify-strategy-order
* Speed limit is 10 times/s (UID)
* Permission: UTA trade (read & write)

Request

```json
curl -X POST "https://api.bitget.com/api/v3/trade/modify-strategy-order" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*" \  
  -H "ACCESS-PASSPHRASE:*" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:zh-CN" \  
  -H "Content-Type: application/json" \  
  -d '{"orderId": "121211212122","qty": "1","tpTriggerBy": "market","takeProfit": "106000","tpOrderType": "market"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| orderId | String | Yes | Order ID Either orderId or clientOid must be provided If both orderId and clientOid are provided simultaneously, orderId takes higher priority |
| clientOid | String | No | Client order ID  Either orderId or clientOid must be provided If both orderId and clientOid are provided simultaneously, orderId takes higher priority |
| qty | String | Yes | Order Quantity Can be modified under partial take-profit/stop-loss mode, and the unit is in the `base coin` |
| tpTriggerBy | String | No | Take-Profit Trigger Type `market`: Market Price `mark`: Mark Price |
| slTriggerBy | String | No | Stop-Loss Trigger Type `market`: Market Price `mark`: Mark Price |
| takeProfit | String | No | Take-Profit Trigger Price |
| stopLoss | String | No | Stop-Loss Trigger Price |
| tpOrderType | String | No | Take-Profit Trigger Strategy Order Type `limit`: Limit Order `market`: Market Order |
| slOrderType | String | No | Stop-Loss Trigger Strategy Order Type `limit`: Limit Order `market`: Market Order |
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