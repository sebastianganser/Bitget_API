# Modify Sub-account API Key

### Description[​](#description "Direct link to Description")

This API is used to modify the unified account sub-account API Key permissions and withdrawal whitelist IP addresses. It only supports modifying the API Key of a unified account sub-account and does not support creating an API Key for a classic account sub-account.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v3/user/update-sub-api
* Rate limit: 10/sec/UID
* Unified account management read and write permissions are required
* Only the main account can call this API

Request

```json
curl -X POST "https://api.bitget.com/api/v3/user/update-sub-api" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json" \  
   -d '{"apiKey":"***********************************","type":"read_write","passphrase":"88888888","permissions":["uta_trade"]}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| apikey | String | Yes | Sub-account API Key |
| passphrase | String | Yes | passphrase A combination of 8 to 32 characters of letters and numbers |
| type | String | No | Permission Type `read_write` Read/Write `read_only` Read-only  **This parameter is required when `permissions` has a value.** |
| permissions | Array | No | permission values   * Unified Account Permissions:  `uta_mgt` Unified Account Management `uta_trade` Unified Account Trading  **This parameter is required when `type` has a value.** |
| ips | Array | No | Withdrawal Whitelist IP   * If not provided, the IP address will not be modified. * If an empty value is provided, the withdrawal whitelist will be deleted.  Multiple IP addresses are supported A maximum of 30 IPs can be bound to a single key **Only supports IPv4** |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1740213448866,  
  "data": {  
    "note": "test",  
    "apiKey": "***********************************",  
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
| apikey | String | Sub-account API Key |
| note | String | Note name |
| type | String | Sub-account API Key Permission Type `read_write` Read/Write `read_only` Read-only |
| permissions | Array | Sub-account API Key Permission Values   * Unified Account Permissions:  `uta_mgt` Unified Account Management `uta_trade` Unified Account Trading |
| ips | Array | Withdrawal Whitelist IP |