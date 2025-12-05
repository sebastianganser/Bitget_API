# Get Upgrade Status

### Description[​](#description "Direct link to Description")

No account type restrictions; both parent and sub-accounts are supported.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/spot/account/upgrade-status
* Rate Limit: 1 req/sec/UID

Request Example

```json
curl "https://api.bitget.com/api/v2/spot/account/upgrade-status" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json"
```

### Request Parameter[​](#request-parameter "Direct link to Request Parameter")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| subUid | String | No | Sub-account User ID |

Response Example

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

### Response Parameter[​](#response-parameter "Direct link to Response Parameter")

| Parameter | Type | Description |
| --- | --- | --- |
| status | String | Upgrade Status  `process`Processing `success`Success `fail`Failed |
| reason | String | Failure Reason  Only returned when the `status = fail` |