# Modify Order

### Description[​](#description "Direct link to Description")

Support modifying orders using either the order ID (orderId) or a custom order ID (clientOid).

* Only orders that have not been fully filled can be modified. If an order has been completely filled, it cannot be
  modified through this interface.
* After submitting a modification request and before receiving the result, repeated modification requests cannot be
  submitted.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v3/trade/modify-order
* Rate limit: 10/sec/UID
* Permission: UTA trade

Request

```json
curl -X POST "https://api.bitget.com/api/v3/trade/modify-order" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*" \  
  -H "ACCESS-PASSPHRASE:*" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:zh-CN" \  
  -H "Content-Type: application/json" \  
  -d '{ "orderId": "1","qty": "123", "price": "123", "autoCancel": "no" }'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameters | Type | Required | Description |
| --- | --- | --- | --- |
| orderId | String | No | Order ID Either orderId or clientOid must be provided If both orderId and clientOid are provided simultaneously, orderId takes higher priority |
| clientOid | String | No | Client order ID  Either orderId or clientOid must be provided If both orderId and clientOid are provided simultaneously, orderId takes higher priority |
| qty | String | No | Order quantity  `Base coin`  Either qty or price must be provided |
| price | String | No | Order price  Either qty or price must be provided |
| autoCancel | String | No | Will the original order be canceled if the order modification fails `yes`: Cancel  `no`: Not cancel（default） |
| symbol | String | No | Symbol name  e.g.,`BTCUSDT` |
| category | String | No | Product type   `SPOT` Spot trading   `MARGIN` Margin trading   `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures |

Response

```json
{  
  "code": "00000",  
  "data": {  
    "orderId": "121212121212",  
    "clientOid": "BITGET#1627293504612"  
  },  
  "msg": "success",  
  "requestTime": 1627293504612  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| orderId | String | Order ID |
| clientOid | String | Client order ID |