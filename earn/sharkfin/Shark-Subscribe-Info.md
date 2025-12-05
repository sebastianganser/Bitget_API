# SharkFin Subscription Detail

Frequency limit: 10c/1s (Uid)

### Description[​](#description "Direct link to Description")

Get subscription detail before subscribe sharkfin.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/earn/sharkfin/subscribe-info

Request Example

```json
curl "https://api.bitget.com/api/v2/earn/sharkfin/subscribe-info?productId=1" \  
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
| productId | String | Yes | Product ID |

Response Example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1696757209022,  
    "data": {  
        "productCoin": "BTC",  
        "subscribeCoin": "USDT",  
        "interestTime": "1697199180000",  
        "expirationTime": "1697803980000",  
        "minPrice": "28000.00",  
        "currentPrice": "30211.23",  
        "maxPrice": "32000.00",  
        "minRate": "5.00",  
        "defaultRate": "1.00",  
        "maxRate": "20.00",  
        "period": "7",  
        "productMinAmount": "0.00100000",  
        "availableBalance": "788",  
        "userAmount": "500.00000000",  
        "remainingAmount": "400.00000000",  
        "profitPrecision": "8",  
        "subscribePrecision": "8"  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| productCoin | String | Product coin |
| subscribeCoin | String | Subscribe coin |
| interestTime | String | Interest start date in Unix timestamp format (in milliseconds) |
| expirationTime | String | Settlement time Unix timestamp format in milliseconds |
| minPrice | String | Minimum price of price range |
| currentPrice | String | Current price |
| maxPrice | String | The maximum price of the price range |
| minRate | String | Minimum rate |
| defaultRate | String | Default rate |
| maxRate | String | Maximum rate |
| period | String | Investment period |
| productMinAmount | String | Product minimum limit |
| availableBalance | String | Available Balance |
| userAmount | String | User quota |
| remainingAmount | String | Remaining balance |
| profitPrecision | String | Interest calculation scale |
| subscribePrecision | String | Subscribe calculation scale |