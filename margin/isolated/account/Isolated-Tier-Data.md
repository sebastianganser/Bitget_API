# Get Isolated Tier Configuration

Frequency limit:10 times/1s (UID)

### Description[​](#description "Direct link to Description")

This interface will determine the user's VIP level based on the User ID sending the request, and then return the tier information based on the VIP level.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/margin/isolated/tier-data

Request Example

```json
curl "https://api.bitget.com/api/v2/margin/isolated/tier-data?symbol=BTCUSDT"  -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*******" \  
   -H "ACCESS-PASSPHRASE:*****" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| symbol | String | Yes | Trading pairs, like BTCUSDT |

Response Example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1694583297872,  
  "data": [  
    {  
      "tier": "1",  
      "symbol": "BTCUSDT",  
      "leverage": "5",  
      "baseCoin": "BTC",  
      "quoteCoin": "USDT",  
      "baseMaxBorrowableAmount": "0",  
      "quoteMaxBorrowableAmount": "0",  
      "maintainMarginRate": "0.1",  
      "initRate": "0.25"  
    }  
  ]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| tier | String | Tier |
| symbol | String | Trading pair |
| leverage | String | Effective leverage, global default: 10x |
| baseCoin | String | Base currency |
| quoteCoin | String | Quote currency |
| baseMaxBorrowableAmount | String | Maximum borrow in base currency |
| quoteMaxBorrowableAmount | String | Maximum borrow in quote currency |
| maintainMarginRate | String | Maintenance margin rate |
| initRate | String | Initial margin rate |