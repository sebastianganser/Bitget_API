# Change The Product Line Leverage

Frequency limit: 5 times/1s (uid)

### Description[​](#description "Direct link to Description")

Adjust the leverage on the given productType

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/mix/account/set-all-leverage

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/mix/account/set-all-leverage" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json" \  
   -d '{"symbol":"btcusdt","productType":"USDT-FUTURES","marginCoin":"usdt","leverage":"20","holdSide":"long"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| productType | String | Yes | Product type `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures |
| leverage | String | Yes | Leverage (Only effective for symbols that have opened positions) |

Response Example

```json
{  
    "code": "00000",  
    "data": "success",  
    "msg": "success",  
    "requestTime": 1627293049406  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| data | String | result success: sueexeeful failure: failed |