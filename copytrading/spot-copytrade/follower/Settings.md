# Add or Modify Following Configurations

Rate Limit: 1 req/sec/UID

### Request Parameter[​](#request-parameter "Direct link to Request Parameter")

* POST /api/v2/copy/spot-follower/settings

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/copy/spot-follower/settings" \  
   -H "ACCESS-KEY:your apiKey" \  
   -H "ACCESS-SIGN:*******" \  
   -H "ACCESS-PASSPHRASE:******" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json" \    
   -d '{  
        "traderId": "abc123",  
        "settings": [{  
                "symbol": "BTCUSDT",  
                "traceType": "amount",  
                "maxHoldSize": "1000",  
                "traceValue": "100",  
                "stopSurplusRatio": "10",  
                "stopLossRatio": "10"  
        }]  
}'
```

### Request Parameter[​](#request-parameter-1 "Direct link to Request Parameter")

| Parameter Name | Parameter Type | Required | Description |
| --- | --- | --- | --- |
| traderId | String | Yes | Trader user ID |
| autoCopy | String | No | Whether to automatically follow new symbol opened by traders(only take effect when parameter mode is basic)   on：auto   off：no |
| mode | String | No | follow mode   basic：basic mode   advanced（default）：advanced mode |
| settings | String | Yes | settings |
| >symbol | String | Yes | Trading pair |
| > traceType | String | Yes | Copy trade type `percent` Set the percentage of the copy trade amount to the trader's elite trade amount. For example, 1 means the follower invests the same amount to open a position as the elite trader, and 2 means the follower invests twice the amount of the elite trader. `amount` The fixed volume specified for copy trading `count` Number of copy trade orders with fixed volume (only take effect when parameter mode is advanced) |
| > maxHoldSize | String | Yes | Maximum following buying quantity |
| > traceValue | String | Yes | Copy trade investment amount  100 or 0.1  TraceType parameter corresponding to the value |
| >stopLossRatio | String | No | The stop-loss ratio can only be a positive integer. 10 means 10%. |
| >stopSurplusRatio | String | No | The take-profit ratio can only be a positive integer. 10 means 10%. |

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