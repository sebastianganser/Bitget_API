# Get Sub-account List

### Description[​](#description "Direct link to Description")

Query Sub-account List

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/user/sub-list
* Rate limit: 10/sec/UID
* Unified account management read permissions are required
* Only the main account can call this API

Request

```json
curl -X GET "https://api.bitget.com/api/v3/user/sub-list?limit=100&cursor=18484" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| limit | String | No | Items per page  The default value is 100, and the maximum value is 100. |
| cursor | String | No | Cursor ID Used for pagination. Do not pass it for the first query. For subsequent queries (second page and beyond), use the cursor returned from the previous query. |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1740212430491,  
  "data": {  
    "list": [  
      {  
        "subUid": "xxx",  
        "username": "llt****@virtual-bitget.com",  
        "status": "normal",  
        "accountMode": "CLASSIC",  
        "type": "VIRTUAL_CHILD",  
        "note": "xxxx",  
        "createdTime": "1740129303268",  
        "updatedTime": "1740129303268"  
      },  
      {  
        "subUid": "xxx",  
        "username": "zml****@virtual-bitget.com",  
        "status": "normal",  
        "accountMode": "UNIFIED",  
        "type": "VIRTUAL_CHILD",  
        "note": "xxx",  
        "createdTime": "1740211445018",  
        "updatedTime": "1740211445018"  
      },  
      {  
        "subUid": "xxx",  
        "username": "tmr****@virtual-bitget.com",  
        "status": "freeze",  
        "accountMode": "UNIFIED",  
        "type": "VIRTUAL_CHILD",  
        "note": "xxx",  
        "createdTime": "1740131800692",  
        "updatedTime": "1740212129476"  
      }  
    ],  
    "hasNext": false,  
    "cursor": "18484"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| cursor | String | Cursor ID |
| hasNext | String | Is there more data on the next page |
| list | Array | Sub-account List |
| > username | String | Sub-account name |
| > subUid | String | Sub-account ID |
| > status | String | Account Status `normal` Normal `frozen` Frozen |
| > accountMode | String | Account Mode `CLASSIC` Classic Account Mode `UNIFIED` Unified Account Mode |
| > type | String | Account Type `COMMON` Regular Sub-account  `VIRTUAL_CHILD` Virtual Sub-account  `ENTRUST_CHILD` Custodial Sub-account |
| > note | String | Note |
| > createdTime | String | Creation Time, Unix Millisecond Timestamp |
| > updatedTime | String | Last Modified Time, Unix Millisecond Timestamp |