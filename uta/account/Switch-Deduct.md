# Switch Deduct

### Description[​](#description "Direct link to Description")

Set BGB deduction.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v3/account/switch-deduct
* Rate limit: 1/sec/UID
* Permission: UTA mgt. (read & write)

Request

```json
curl -X POST "https://api.bitget.com/api/v3/account/switch-deduct" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json" \  
   -d '{"deduct":"on"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| deduct | String | Yes | Is it enabled `on` enabled `off` disabled |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1728625799912,  
  "data": true  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

N/A