# Get Trader's Current Trading Pair

Limit rule 10 times/1s (uid)

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/copy/spot-follower/query-trader-symbols

Request Example

```json
curl "https://api.bitget.com/api/v2/copy/spot-follower/query-trader-symbols?traderId=123" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*******" \  
  -H "ACCESS-PASSPHRASE:*****" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json"
```

### Request Parameter[​](#request-parameter "Direct link to Request Parameter")

| Parameter Name | Parameter Type | Required | Description |
| --- | --- | --- | --- |
| traderId | String | Yes | trader Id |

Response example

```json
{  
        "code": "00000",  
        "data": {  
                "currentTradingList": ["ETHUSDT", "BTCUSDT"]  
        },  
        "msg": "success",  
        "requestTime": 1627354109502  
}
```

### Response Description[​](#response-description "Direct link to Response Description")

| Parameter | Parameter Type | Description |
| --- | --- | --- |
| currentTradingList | List<String> | Current copy trading pairs |