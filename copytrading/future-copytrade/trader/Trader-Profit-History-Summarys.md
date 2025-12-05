# Get History Profit Summary

Rate Limit: 5 req/sec/UID

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/copy/mix-trader/profit-history-summarys

Request Example

```json
curl "https://api.bitget.com/api/v2/copy/mix-trader/profit-history-summarys" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*******" \  
  -H "ACCESS-PASSPHRASE:*****" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

N/A

Response example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1698200382922,  
  "data": {  
    "profitSummary": {  
      "yesterdayProfit": "0",  
      "sumProfit": "26.4519",  
      "waitProfit": "0",  
      "yesterdayTime": "1698076800000"  
    },  
    "profitHistoryList": [  
      {  
        "coin": "USDT",  
        "profitCount": "24.28410397",  
        "lastProfitTime": "1698076800000"  
      }  
    ]  
  }  
}
```

### Response parameters[​](#response-parameters "Direct link to Response parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| profitSummary | Object | Elite trader profit share overview |
| >yesterdayProfit | String | Yesterday's profit share (elite trader) |
| >yesterdayTime | String | Yesterday's profit sharing time (milliseconds) |
| >sumProfit | String | Profit share in total |
| >waitProfit | String | To be shared |
| profitHistoryList | List | Trader profit sharing summary information |
| >coin | String | Settlement currency (in cryptocurrency) |
| >profitCount | String | Profit overview (in cryptocurrency) |
| >lastProfitTime | String | The last time to distribute profit share (milliseconds) (in cryptocurrency) |