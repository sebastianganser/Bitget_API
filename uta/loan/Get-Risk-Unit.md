# Get Risk Unit

### Description[​](#description "Direct link to Description")

Get Risk Unit,Only the parent account API Key can use this endpoint

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/ins-loan/risk-unit
* Rate limit: 3/sec/UID
* Permission: UTA mgt. (read)

Request

```json
curl "https://api.bitget.com/api/v3/ins-loan/risk-unit" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

N/A

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1745725444960,  
  "data": {  
    "riskUnitId": [  
      "1222222222",  
      "1222222223"  
    ]  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| riskUnitId | Array | All Risk Unit Ids |