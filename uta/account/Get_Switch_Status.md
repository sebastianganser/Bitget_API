# Get Switch Status

### Description[​](#description "Direct link to Description")

Only supports parent accounts.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/account/switch-status
* Rate limit: 5/sec/UID

Request

```json
curl "https://api.bitget.com/api/v3/account/switch-status" \  
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
  "requestTime": 1746687063471,  
  "data": {  
    "status": "fail",  
    "reason": "upgrade_disabled"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| status | String | Switch Status  `process`Processing `success`Success `fail`Failed |
| reason | String | Failure Reason  Only returned when the `status = fail` |