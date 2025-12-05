# Freeze/Unfreeze Sub-account

### Description[​](#description "Direct link to Description")

Freeze/Unfreeze Sub-account

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v3/user/freeze-sub
* Rate limit: 10/sec/UID
* Unified account management read and write permissions are required
* Only the main account can call this API

Request

```json
curl -X POST "https://api.bitget.com/api/v3/user/freeze-sub" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json" \  
   -d '{"subUid":"xxxx","operation":"freeze"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| subUid | String | Yes | Sub-account ID to be frozen/unfrozen |
| operation | String | Yes | Operation Type： `freeze` Freeze `unfreeze` Unfreeze |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1740212117457,  
  "data": {}  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

N/A