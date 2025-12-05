# Batch Modify Orders

### Description[​](#description "Direct link to Description")

* Supports batch order modification via API, allowing simultaneous submission of multiple orders across different
  trading pairs (limited to orders within the same business line).
* Each request supports modification of up to 20 orders.
* Supports continuous order modification, meaning additional modification requests can be submitted before the previous
  modification request is completed. A maximum of 5 consecutive modification requests for in-progress orders can be
  submitted, and the matching engine will process the modification requests in sequence.
* Within the same batch of modification requests, each order can only appear once.
* Only fully unfilled orders can have their price and quantity modified.
* Partially filled orders can have their price and quantity modified (the modified quantity cannot be less than the
  already filled quantity).
* Modification of reduce-only orders is not supported.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v3/trade/batch-modify-order
* Rate limit: 10/sec/UID
* Permission: UTA trade

Request

```json
curl -X POST "https://api.bitget.com/api/v3/trade/batch-modify-order" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*" \  
  -H "ACCESS-PASSPHRASE:*" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:zh-CN" \  
  -H "Content-Type: application/json" \  
  -d '[{ "orderId": "1","qty": "123", "price": "123", "autoCancel": "no" },{ "orderId": "2","qty": "123", "price": "123", "autoCancel": "no" }]'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameters | Type | Required | Description |
| --- | --- | --- | --- |
| orderId | String | No | Order ID Either orderId or clientOid must be provided If both orderId and clientOid are provided simultaneously, orderId takes higher priority |
| clientOid | String | No | Client order ID  Either orderId or clientOid must be provided If both orderId and clientOid are provided simultaneously, orderId takes higher priority |
| qty | String | No | Order quantity  `Base coin` |
| price | String | No | Order price |
| autoCancel | String | No | Will the original order be canceled if the order modification fails `yes`: Cancel  `no`: Not cancel（default） |
| symbol | String | No | Symbol name  e.g.,`BTCUSDT` |
| category | String | No | Product type   `SPOT` Spot trading   `MARGIN` Margin trading   `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures |

Response

```json
{  
  "code": "00000",  
  "data": [  
    {  
      "orderId": "1",  
      "clientOid": "12312"  
    },  
    {  
      "orderId": "2",  
      "clientOid": "2321"  
    }  
  ],  
  "msg": "success",  
  "requestTime": 1627293504612  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| orderId | String | Order ID |
| clientOid | String | Client order ID |