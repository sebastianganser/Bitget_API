# Modify Take Profit and Stop Loss

Rate Limit: 1 req/sec/UID

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/copy/spot-trader/order-modify-tpsl

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/copy/spot-trader/order-modify-tpsl" \  
   -H "ACCESS-KEY:your apiKey" \  
   -H "ACCESS-SIGN:*******" \  
   -H "ACCESS-PASSPHRASE:*****" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json" \    
   -d '{"trackingNo": "123","stopSurplusPrice": "2000","stopLossPrice": "1000"}'
```

### Request Parameter[​](#request-parameter "Direct link to Request Parameter")

| Parameter Name | Parameter Type | Required | Description |
| --- | --- | --- | --- |
| trackingNo | String | Yes | Track order number |
| stopSurplusPrice | String | No | One of stopSurplusPrice and stopLossPrice must be passed. TP price When it is empty, it is ignored or not updated, no matter take-profit exists or not, When it is 0, it means the original take-profit is canceled if there is a take-profit already. When it is greater than or equal to 0, it means take-profit is updated or set. |
| stopLossPrice | String | No | One of stopSurplusPrice and stopLossPrice must be passed. When it is empty, it is ignored or not updated, no matter stop-loss exists or not, When it is 0, it means the original stop-loss is canceled if there is a stop-loss already. When it is greater than or equal to 0, it means stop-loss is updated or set. |

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