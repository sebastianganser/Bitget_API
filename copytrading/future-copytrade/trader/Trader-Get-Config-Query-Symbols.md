# Get Copy Trade Symbol Settings

Rate limit: 5 req/sec/UID

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/copy/mix-trader/config-query-symbols

Request Example

```json
curl "https://api.bitget.com/api/v2/copy/mix-trader/config-query-symbols?productType=usdt-futures" \  
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
| productType | String | Yes | Product type `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures |

Response example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1695807225928,  
  "data": [  
    {  
      "symbol": "BTCUSDT",  
      "openTrader": "yes",  
      "minOpenCount": "0.002",  
      "maxLeverage": "50",  
      "stopSurplusRatio": "100",  
      "stopLossRatio": "30"  
    }  
  ]  
}
```

### Response parameters[​](#response-parameters "Direct link to Response parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| symbol | String | Trading pair |
| openTrader | String | Activates copy trading or not, `YES`, `NO` |
| minOpenCount | String | Minimum opening amount of elite traders |
| maxLeverage | String | Maximum leverage |
| stopSurplusRatio | String | Value set for take profit (value is a positive integer, 120 means 120%) |
| stopLossRatio | String | Value set for stop-loss ratio (the value is a positive integer, 40 means 40%) |