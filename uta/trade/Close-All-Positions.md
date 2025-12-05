# Close All Positions

### Description[​](#description "Direct link to Description")

Close positions by position side or category. All positions will be closed at market price, subject to slippage.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v3/trade/close-positions
* Rate limit: 5/sec/UID
* Permission: UTA trade (read & write)

Request

```json
curl -X POST "https://api.bitget.com/api/v3/trade/close-positions" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*" \  
  -H "ACCESS-PASSPHRASE:*" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:zh-CN" \  
  -H "Content-Type: application/json" \  
  -d '{"category":"USDT-FUTURES"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| category | String | Yes | Product type   `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures |
| symbol | String | No | Symbol name  e.g.,`BTCUSDT` If no symbol is provided, all positions in the corresponding category will be closed. |
| posSide | String | No | Position side  `long`/`short`   If this field is provided, only the position in the corresponding side will be closed. |

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