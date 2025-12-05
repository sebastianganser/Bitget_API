# Get Union Config

Rate limits: 1 time/1s (uid)

### Description[​](#description "Direct link to Description")

Get API for union margin configuration parameters (Liability Initial Margin Rate, Liability Maintenance Margin Rate,
Personal Liability Limit, Personal Liability Limit Ratio)

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/mix/account/union-config

Request

```json
curl "https://api.bitget.com/api/v2/mix/account/union-config" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

无

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1627293357336,  
  "data": {  
    "imr": "0.1",  
    "mmr": "0.05",  
    "individualLimit": "10000",  
    "individualLimitRatio": "0.8"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| imr | String | Liability Initial Margin Rate Decimal format. Fixed value: 0.1 |
| mmr | String | Liability Maintenance Margin Rate Decimal format. Fixed value: 0.05 |
| individualLimit | String | Personal Liability Limit Unit: USDT |
| individualLimitRatio | String | Personal Liability Limit Ratio Decimal format. E.g., 0.8 represents 80% |