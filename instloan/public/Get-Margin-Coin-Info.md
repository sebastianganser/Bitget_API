# Get Margin Coin Info

Rate limit: 5 req/sec/UID

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/spot/ins-loan/ensure-coins-convert

Request Example

```json
curl "https://api.bitget.com/api/v2/spot/ins-loan/ensure-coins-convert?productId=xxx" \  
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
| productId | String | Yes | Product Id |

Response Example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1711697581815,  
  "data": {  
    "productId": "xxxxxxxx",  
    "coinInfo": [  
      {  
        "coin": "USDC",  
        "convertRatio": "1",  
        "maxConvertValue": "1000"  
      },  
      {  
        "coin": "USDT",  
        "convertRatio": "1",  
        "maxConvertValue": "1000"  
      },  
      {  
        "coin": "BTC",  
        "convertRatio": "0.99",  
        "maxConvertValue": "1000"  
      },  
      {  
        "coin": "ETH",  
        "convertRatio": "0.99",  
        "maxConvertValue": "1000"  
      }  
    ]  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| productId | String | Product Id |
| coinInfo | Array | Spot margin coin |
| > coin | String | Margin coin |
| > convertRatio | String | Margin coin convert ratio |
| > maxConvertValue | String | Maximum convert value(USDT) |