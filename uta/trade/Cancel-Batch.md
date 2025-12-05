# Batch Cancel

### Description[​](#description "Direct link to Description")

* This endpoint allows you to cancel a multiple unfilled or partially filled order across spot, margin, and futures
  markets.
* When making a batch order cancellation, ensure that each request uses either orderId or clientOid for identification — never both. If both orderId and clientOid are provided in a single request, the clientOid will be ignored.
* Batch order cancellation allows partial success.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v3/trade/cancel-batch
* Rate limit: 5/sec/UID
* Batch limit: No more than 20 orders per batch
* Permission: UTA trade (read & write)

Request

```json
curl -X POST "https://api.bitget.com/api/v3/trade/cancel-batch" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*" \  
  -H "ACCESS-PASSPHRASE:*" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:zh-CN" \  
  -H "Content-Type: application/json" \  
  -d '[{"orderId":"112233","category":"spot","symbol":"BTCUSDT"},{"clientOid":"123456","category":"spot","symbol":"BTCUSDT"}]'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| orderId | String | No | Order ID Either `clientOid` or `orderId` must be provided. If both are present or do not match, `orderId` will take priority |
| clientOid | String | No | Client order ID Either `clientOid` or `orderId` must be provided. If both are present or do not match, `orderId` will take priority |
| category | String | YES | Product type   `SPOT` Spot trading   `MARGIN` Margin trading   `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures  All orders must have the same category |
| symbol | String | YES | Symbol name  e.g.,`BTCUSDT` |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1695806875837,  
  "data": [  
    {  
      "clientOid": "121211212122",  
      "orderId": "111111111111111111"  
    },  
    {  
      "clientOid": "121211212123",  
      "orderId": "111111111111111114"  
    }  
  ]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| orderId | String | Order ID |
| clientOid | String | Client order ID |
| code | String | Error code for this order |
| msg | String | Error message for this order |