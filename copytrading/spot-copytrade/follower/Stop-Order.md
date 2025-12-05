# Stop The Order

Rate Limit: 1 req/sec/UID

### Request Parameter[​](#request-parameter "Direct link to Request Parameter")

* POST /api/v2/copy/spot-follower/stop-order

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/copy/spot-follower/stop-order" \  
   -H "ACCESS-KEY:your apiKey" \  
   -H "ACCESS-SIGN:*******" \  
   -H "ACCESS-PASSPHRASE:*****" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json" \    
   -d '{  
        "trackingNoList": ["123"]  
}'
```

### Request Parameter[​](#request-parameter-1 "Direct link to Request Parameter")

| Parameter Name | Parameter Type | Required | Description |
| --- | --- | --- | --- |
| trackingNoList | String | Yes | Order tracking number groups Up to 50. Atomic execution results, either all successful or all failed. |

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