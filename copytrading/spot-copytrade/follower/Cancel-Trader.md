# Cancel Follow

Rate Limit: 1 req/sec/UID

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/copy/spot-follower/cancel-trader

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/copy/spot-follower/cancel-trader" \  
   -H "ACCESS-KEY:your apiKey" \  
   -H "ACCESS-SIGN:*******" \  
   -H "ACCESS-PASSPHRASE:*****" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json" \    
   -d '{  
        "traderId": "123"  
}'
```

### Request Parameter[​](#request-parameter "Direct link to Request Parameter")

| Parameter Name | Parameter Type | Required | Description |
| --- | --- | --- | --- |
| traderId | String | Yes | Trader user ID |

Response example

```json
{  
        "code": "00000",  
        "msg": "success",  
        "requestTime": 1656066841304,  
        "data": ""  
}
```

### Response Description[​](#response-description "Direct link to Response Description")

| Parameter | Parameter Type | Description |
| --- | --- | --- |
| code | String | Result code `00000`success others fail |