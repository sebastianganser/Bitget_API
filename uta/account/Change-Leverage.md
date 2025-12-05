# Set Leverage

### Description[​](#description "Direct link to Description")

This endpoint allows you to set leverage.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v3/account/set-leverage
* Rate limit: 10/sec/UID
* Permission: UTA mgt. (read & write)

Request

```json
curl -X POST "https://api.bitget.com/api/v3/account/set-leverage" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json" \  
   -d '{"category":"USDT-FUTURES","symbol":"EOSUSDT","leverage":"10"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| category | String | Yes | Product type  `MARGIN` Margin trading `USDT-FUTURES` USDT futures  `COIN-FUTURES`Coin-M futures `USDC-FUTURES` USDC futures |
| symbol | String | No | Symbol name  This field is required to set leverage for futures |
| leverage | String | Yes | Leverage multiple |
| coin | String | No | Coin name  This field is required to set leverage for margin trading |
| posSide | String | No | Position side  `long`/`short`  This field is required to set leverage for isolated margin |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1728625799912,  
  "data": "success"  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

N/A