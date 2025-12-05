# Get Sub-account API Keys

### Description[​](#description "Direct link to Description")

Supports querying the full API Key list under a single sub-account.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/user/sub-api-list
* Rate limit: 10/sec/UID
* Unified account management read permissions are required
* Only the main account can call this API

Request

```json
curl -X GET "https://api.bitget.com/api/v3/user/api/v3/user/sub-api-list?subUid=4746345901&limit=100" \  
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
| subUid | String | Yes | Sub-account UID |
| limit | String | No | Items per page  The default value is 100, and the maximum value is 100. |
| cursor | String | No | Cursor ID Used for pagination. Do not pass it for the first query. For subsequent queries (second page and beyond), use the cursor returned from the previous query. |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1740212430491,  
  "data": {  
    "items": [  
      {  
        "apiKey": "***********************************",  
        "note": "xxxx",  
        "type": "read_only",  
        "permissions": [  
          "uta_trade"  
        ],  
        "ips": [  
          "127.0.0.1"  
        ],  
        "ts": "1740129303268"  
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
| items | Array | Sub-account API Key List |
| > apikey | String | Sub-account API Key |
| > type | String | Sub-account API Key Permission Type `read_write` Read/Write `read_only` Read-only |
| > note | string | Note name |
| > permissions | Array | Sub-account API Key Permission Values   * Unified Account Permissions:  `uta_mgt` Unified Account Management `uta_trade` Unified Account Trading |
| > ips | Array | Withdrawal Whitelist IP |