# Get Product Info

### Description[​](#description "Direct link to Description")

Get Product Info

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/ins-loan/product-infos
* Rate limit: 3/sec/UID
* Permission: UTA mgt. (read)

Request

```json
curl "https://api.bitget.com/api/v3/ins-loan/product-infos?productId=xxxxxxxx" \  
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
| productId | String | Yes | Product Id |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1711697573019,  
  "data": {  
    "productId": "xxxxxxxx",  
    "leverage": "2",  
    "supportUsdtContract": "YES",  
    "supportCoinContract": "YES",  
    "supportUsdcContract": "YES",  
    "transferLine": "0.6667",  
    "spotBuyLine": "0.8",  
    "usdtContractOpenLine": "0.8",  
    "coinContractOpenLine": "0.8",  
    "usdcContractOpenLine": "0.8",  
    "liquidationLine": "0.9",  
    "stopLiquidationLine": "0.75"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| productId | String | Product Id |
| leverage | String | The maximum leverage for this loan product. 2x/4x |
| supportUsdtContract | String | Whether USDT-M Futures are supported. YES/NO |
| supportCoinContract | String | Whether Coin-M Futures are supported. YES/NO |
| supportUsdcContract | String | Whether USDC-M Futures are supported. YES/NO |
| transferLine | String | Restrict line for transfer, eg: 0.6667 |
| spotBuyLine | String | Restrict line for Spot buy, eg: 0.8 |
| usdtContractOpenLine | String | Restrict line for USDT-M Futures open position, eg: 0.8 |
| coinContractOpenLine | String | Restrict line for Coin-M Futures open position, eg: 0.8 |
| usdcContractOpenLine | String | Restrict line for USDC-M Futures open position, eg: 0.8 |
| liquidationLine | Array | Line for liquidation, eg: 0.9 |
| stopLiquidationLine | String | Line for stop liquidation, eg: 0.75 |