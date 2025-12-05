# Get Isolated Risk Rate

Frequency limit: 10 times/1s (UID)

### Description[​](#description "Direct link to Description")

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/margin/isolated/account/risk-rate

Request Example

```json
curl "https://api.bitget.com/api/v2/margin/isolated/account/risk-rate?symbol=BTCUSDT" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*******" \  
   -H "ACCESS-PASSPHRASE:*****" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json" \
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| symbol | String | No | Trading pairs, like BTCUSDT |
| pageNum | String | No | Page number, Default: 1 |
| pageSize | String | No | Size per page, default 100, maximum 500 |

Response Example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1694590583906,  
  "data": [  
    {  
      "symbol": "BTCUSDT",  
      "riskRateRatio": "0"  
    }  
  ]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| symbol | String | Trading pair |
| riskRateRatio | String | Risk ratio (total assets/total liabilities under isolated mode) |