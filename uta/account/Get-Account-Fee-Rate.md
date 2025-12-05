# Get Account Fee Rate

### Description[​](#description "Direct link to Description")

Get Account Fee Rate

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/account/fee-rate
* Rate limit: 3/sec/UID
* Unified account management read permissions are required

Request

```json
curl "https://api.bitget.com/api/v3/account/fee-rate?symbol=BTCUSDT&category=SPOT" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| symbol | String | Yes | Symbol  e.g.,`BTCUSDT` |
| category | String | Yes | Product type   `SPOT` Spot trading   `MARGIN` Margin trading   `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1751972326323,  
  "data": {  
    "makerFeeRate": "0.0008",  
    "takerFeeRate": "0.0008"  
  }  
}
```

### Response Example[​](#response-example "Direct link to Response Example")

| Parameters | Type | Description |
| --- | --- | --- |
| makerFeeRate | String | Maker fee rate In decimal form, e.g., 0.0002 represents 0.02% |
| takerFeeRate | String | Taker fee rate In decimal form, e.g., 0.0002 represents 0.02% |