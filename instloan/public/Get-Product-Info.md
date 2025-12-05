# Get Product Info

Rate limit: 5 req/sec/UID

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/spot/ins-loan/product-infos

Request Example

```json
curl "https://api.bitget.com/api/v2/spot/ins-loan/product-infos?productId=xxx" \  
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
  "requestTime": 1711697573019,  
  "data": {  
    "productId": "xxxxxxxx",  
    "leverage": "2",  
    "transferLine": "0.6667",  
    "spotBuyLine": "0.8",  
    "liquidationLine": "0.9",  
    "stopLiquidationLine": "0.75"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| productId | String | Product Id |
| leverage | String | The maximum leverage for this loan product. 2x/4x |
| transferLine | String | Restrict line for transfer, eg: 0.6667 |
| spotBuyLine | String | Restrict line for Spot buy, eg: 0.8 |
| liquidationLine | String | Line for liquidation, eg: 0.9 |
| stopLiquidationLine | String | Line for stop liquidation, eg: 0.75 |