# Delete Subaccount ApiKey

Frequency limit:10 times/1s (User ID)

### Description[​](#description "Direct link to Description")

Only applicable for ND broker main-account

Delete ApiKey for the specified subaccount

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/broker/manage/delete-subaccount-apikey

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/broker/manage/delete-subaccount-apikey" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*" \  
  -H "ACCESS-PASSPHRASE:*" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:zh-CN" \  
  -H "Content-Type: application/json" \  
  -d '{"subUid": "xxxxxxx","apiKey": "xxxxxx"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| subUid | String | Yes | Sub account UID |
| apiKey | String | Yes | API Key |

Response Example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1739774869632,  
    "data": "success"  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| data | String | success: delete successed |