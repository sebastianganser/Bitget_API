# Cancel All Orders

### Description[​](#description "Direct link to Description")

Cancel unfilled or partially filled orders by symbol or category.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v3/trade/cancel-symbol-order
* Rate limit: 5/sec/UID
* Permission: UTA trade (read & write)

Request

```json
curl -X POST "https://api.bitget.com/api/v3/trade/cancel-symbol-order" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*" \  
  -H "ACCESS-PASSPHRASE:*" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:zh-CN" \  
  -H "Content-Type: application/json" \  
  -d '{"category":"SPOT"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| category | String | Yes | Product type   `SPOT` Spot trading   `MARGIN` Margin trading   `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures |
| symbol | String | No | Symbol name  e.g.,`BTCUSDT` If no symbol is provided, all pending orders in the corresponding category will be closed. |

Response

```json
{  
  "code": "00000",  
  "data": {  
    "list": [  
      {  
        "orderId": "111111111111111111",  
        "clientOid": "111111111111111111",  
        "code": "24056",  
        "msg": "notExisted"  
      }  
    ]  
  },  
  "msg": "success",  
  "requestTime": 1627293504612  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| list | String | List |
| >orderId | String | Order ID |
| >clientOid | String | Client order ID |
| >msg | String | Message |
| >code | String | Code |