# Get Risk Unit

Rate limit: 5 req/sec/UID

### Description[​](#description "Direct link to Description")

Only the parent account API Key can use this endpoint

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/spot/ins-loan/risk-unit

Request Example

```json
curl "https://api.bitget.com/api/v2/spot/ins-loan/risk-unit" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*******" \  
  -H "ACCESS-PASSPHRASE:*****" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

N/A

Response Example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1711697588556,  
  "data": {  
    "riskUnitId": [  
        "xxxxxxxx",  
        "xxxxxxxx"  
    ]  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| riskUnitId | List | Risk Unit IDs |