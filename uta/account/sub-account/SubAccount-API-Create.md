# Create Sub-account API Key

### Description[​](#description "Direct link to Description")

This API is used to create an API Key for a sub-account under a unified account. It is applicable when the main
account is in a mix or unified account mode. If the current main account is in the classic account mode, this API
cannot be called.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v3/user/create-sub-api
* Rate limit: 10/sec/UID
* Unified account management read and write permissions are required
* Only the main account can call this API

Request

```json
curl -X POST "https://api.bitget.com/api/v3/user/create-sub-api" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json" \  
   -d '{"subUid":"xxx","note":"xxx","type":"read_only","permissions":["uta_trade"],"passphrase":"1234567Aa","ips":["127.0.0.1"]}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| subUid | String | Yes | Sub-account ID |
| note | String | Yes | Note Name The note needs to start with a letter and supports [0-9], [a-z], [A-Z], as well as [-,\_] |
| type | String | Yes | Permission Type `read_write` Read/Write `read_only` Read-only |
| passphrase | String | Yes | passphrase A combination of 8 to 32 characters of letters and numbers |
| permissions | Array | Yes | permission values   * Unified Account Permissions:  `uta_mgt` Unified Account Management `uta_trade` Unified Account Trading |
| ips | Array | Yes | Withdrawal Whitelist IP Multiple IP addresses are supported A maximum of 30 IPs can be bound to a single key **Only supports IPv4** |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1740213448866,  
  "data": {  
    "note": "test",  
    "apiKey": "***********************************",  
    "secret": "*****************************************",  
    "type": "read_only",  
    "permissions": [  
      "uta_trade"  
    ],  
    "ips": [  
      "127.0.0.1"  
    ]  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| note | String | note |
| apikey | String | Sub-account API Key |
| secret | String | Sub-account API Secret |
| type | String | Sub-account API Key Permission Type `read_write` Read/Write `read_only` Read-only |
| permissions | Array | Sub-account API Key Permission Values   * Unified Account Permissions:  `uta_mgt` Unified Account Management `uta_trade` Unified Account Trading |
| ips | Array | Withdrawal Whitelist IP |