# Unfollow the Trader

Rate Limit: 5 req/sec/UID

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/copy/mix-follower/cancel-trader

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/copy/mix-follower/cancel-trader" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*******" \  
  -H "ACCESS-PASSPHRASE:*****" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json" \  
  -d '{"traderId": "123123"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| traderId | String | Yes | Trader user ID |

Response example

```json
{  
    "code": "00000",  
    "data": "success",  
    "msg": "success",  
    "requestTime": 1627354109502  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| data | String | Result `success` `fail` |