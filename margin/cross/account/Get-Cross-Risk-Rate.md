# Get Cross Risk Rate

Frequency limit: 10 times/1s (UID)

### Description[​](#description "Direct link to Description")

Get cross risk rate

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/margin/crossed/account/risk-rate

Request Example

```json
curl "https://api.bitget.com/api/v2/margin/crossed/account/risk-rate" \  
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
| N/A |  |  |  |

Response Example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1695636742119,  
  "data": {  
    "riskRateRatio": "0"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| riskRate | String | Risk ratio (total assets/total liabilities under cross mode) |