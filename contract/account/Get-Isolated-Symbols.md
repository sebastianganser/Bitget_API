# Get Isolated Symbols

Rate limits: 10 time/1s (uid)

### Description[​](#description "Direct link to Description")

Retrieve trading pairs with isolated margin mode under the account.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/mix/account/isolated-symbols

Request

```json
curl "https://api/v2/mix/account/isolated-symbols?productType=USDT-FUTURES" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| productType | String | Yes | Product type `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1761568886493,  
  "data": [  
    {  
      "symbol": "COAIUSDT",  
      "marginMode": "isolated"  
    },  
    {  
      "symbol": "EVAAUSDT",  
      "marginMode": "isolated"  
    }  
  ]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| symbol | String | Symbol name |
| marginMode | String | The margin mode is fixed as `isolated` |