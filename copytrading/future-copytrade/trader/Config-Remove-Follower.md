# Remove Follower

Rate limit: 5 req/sec/UID

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/copy/mix-trader/config-remove-follower

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/copy/mix-trader/config-remove-follower" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*******" \  
  -H "ACCESS-PASSPHRASE:*****" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json" \  
  -d '{"followerUid": "123123"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| followerUid | String | Yes | Follower UID |

Response example

```json
{  
    "code": "00000",  
    "data": "success",  
    "msg": "success",  
    "requestTime": 1627354109502  
}
```

### Response parameters[​](#response-parameters "Direct link to Response parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| data | String | success |