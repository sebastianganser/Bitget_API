# Cancel Order

### Description[​](#description "Direct link to Description")

This endpoint allows you to cancel a single unfilled or partially filled order across spot, margin, and futures markets.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v3/trade/cancel-order
* Rate limit: 10/sec/UID
* Permission: UTA trade (read & write)

Request

```json
curl -X POST "https://api.bitget.com/api/v3/trade/cancel-order" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*" \  
  -H "ACCESS-PASSPHRASE:*" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:zh-CN" \  
  -H "Content-Type: application/json" \  
  -d '{"orderId":"111111111111111111"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| orderId | String | No | Order ID Either `clientOid` or `orderId` must be provided. If both are present or do not match, `orderId` will take priority |
| clientOid | String | No | Client order ID Either `clientOid` or `orderId` must be provided. If both are present or do not match, `orderId` will take priority |
| category | String | No | Product type   `SPOT` Spot trading   `MARGIN` Margin trading   `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1695806875837,  
  "data": {  
    "clientOid": "121211212122",  
    "orderId": "111111111111111111"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| orderId | String | Order ID |
| clientOid | String | Client order ID |