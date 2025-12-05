# Create Sub-account

### Description[​](#description "Direct link to Description")

* This API is used for the main account to create a sub-account. It only supports creating unified account virtual sub-accounts and does not support creating regular sub-accounts.
* The newly created sub-account will be in Unified Account - Basic Mode by default. To switch to Advanced Mode, please set it manually on the web page.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v3/user/create-sub
* Rate limit: 10/sec/UID
* Unified account management read and write permissions are required
* Only the main account can call this API

Request

```json
curl -X POST "https://api.bitget.com/api/v3/user/create-sub" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json" \  
   -d '{"username":"xxxx","accountMode":"unified","note":"xxx"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| username | String | Yes | Generate a virtual email address username. It can only contain lowercase letters and cannot exceed 20 characters. |
| accountMode | String | No | Sub-account Mode `classic` Classic Account Sub-account `unified` Unified Account Sub-account |
| note | String | No | Note, cannot exceed 50 characters. |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1740211442920,  
  "data": {  
    "username": "xxxx@virtual-bitget.com",  
    "subUid": "xxxx",  
    "status": "normal",  
    "note": "xxxx",  
    "createdTime": "1740211445041",  
    "updatedTime": "1740211445041"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| username | String | Virtual Email Address |
| subUid | String | Virtual Sub-account ID |
| status | String | Account Status `normal` |
| note | String | Note |
| createdTime | String | Creation Time, Unix Millisecond Timestamp |
| updatedTime | String | Last Modified Time, Unix Millisecond Timestamp |