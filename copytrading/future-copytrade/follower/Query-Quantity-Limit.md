# Get Follow Limit

Frequency limit: 10 times/1s (IP)

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/copy/mix-follower/query-quantity-limit

Request Example

```json
curl "https://api.bitget.com/api/v2/copy/mix-follower/query-quantity-limit?productType=usdt-futures&symbol=BTCUSDT" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*******" \  
  -H "ACCESS-PASSPHRASE:*****" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| symbol | String | No | Trading pair |
| productType | String | Yes | Product type `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures |

Response example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1695812926981,  
    "data": [  
        {  
            "maxFollowSize": "20000",  
            "minFollowSize": "0.005",  
            "symbol": "BTCUSDT"  
        }  
    ]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| maxFollowSize | String | Maximum order size to place (trading currency) |
| minFollowSize | String | Minimum order size to place (trading currency) |
| symbol | String | Trading pair |