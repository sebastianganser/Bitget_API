# Delete Sub-account API Key

### Description[​](#description "Direct link to Description")

This API is used for the main account to delete a sub-account's API Key. It is not applicable for the main account or
sub-account to delete their own API Key.

Please note that once the deletion is completed, the sub-account API Key will be immediately invalid. Before performing
the deletion, ensure that this operation will not cause any loss.

This API only supports deleting API Keys of sub-accounts under a unified account, and does not support deleting API Keys
of sub-accounts under a classic account.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v3/user/delete-sub-api
* Rate limit: 10/sec/UID
* Unified account management read and write permissions are required
* Only the main account can call this API

Request

```json
curl -X POST "https://api.bitget.com/api/v3/user/delete-sub-api" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json" \  
   -d '{"apiKey":"***********************************"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| apikey | String | yes | The sub-account API Key |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1740213448866,  
  "data": {}  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

N/A