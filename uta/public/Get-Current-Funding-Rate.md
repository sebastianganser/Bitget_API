# Get Current Funding Rate

### Description[​](#description "Direct link to Description")

Get current funding rate.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/market/current-fund-rate
* Rate limit: 20次/sec/IP

Request

```json
curl "https://api.bitget.com/api/v3/market/current-fund-rate?symbol=BTCUSDT" \
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| symbol | String | Yes | Trading pair, based on the symbolName, i.e. BTCUSDT |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1743059269376,  
  "data": [  
    {  
      "symbol": "BTCUSDT",  
      "fundingRate": "0.000071",  
      "fundingRateInterval": "8",  
      "nextUpdate": "1743062400000",  
      "minFundingRate": "-0.003",  
      "maxFundingRate": "0.003"  
    }  
  ]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| >symbol | String | Trading pair name |
| >fundingRate | String | Current funding rates |
| >fundingRateInterval | String | Funding rate settlement period Unit: hour. Enumeration values include 1, 2, 4, 8. 1 represents 1 hour, 2 represents 2 hours, and so on. |
| >nextUpdate | String | Next update time Unix timestamp in milliseconds |
| >minFundingRate | String | Lower limit of funding rate  Returned in decimal form. 0.025 represents 2.5%. |
| >maxFundingRate | String | Upper limit of funding rate  Returned in decimal form. 0.025 represents 2.5%. |