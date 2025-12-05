# Get Deduct Info

### Description[​](#description "Direct link to Description")

Get BGB deduction status.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/account/deduct-info
* Rate limit: 1/sec/UID
* Permission: UTA mgt. (read)

Request

```json
curl "https://api.bitget.com/api/v3/account/deduct-info" \  
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
    "deduct": "on"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| deduct | String | Is it enabled `on` enabled `off` disabled |