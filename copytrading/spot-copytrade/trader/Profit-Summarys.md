# Get Profit Summary

Rate Limit: 5 req/sec/UID

Get basic information on traders' profits and a summary of historical profits.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/copy/spot-trader/profit-summarys

Request Example

```json
curl "https://api.bitget.com/api/v2/copy/spot-trader/profit-summarys" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*******" \  
  -H "ACCESS-PASSPHRASE:*****" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json"
```

### Request Parameter[​](#request-parameter "Direct link to Request Parameter")

N/A

Response example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1695806592362,  
    "data": {  
        "profitSummarys": {  
            "yesterdayProfit": "0",  
            "yesterdayTime": "1695720000000",  
            "sumProfit": "4.5837",  
            "waitProfit": "0"  
        },  
        "profitHistoryList": [  
            {  
                "coin": "USDT",  
                "profitCount": "4.58376728",  
                "lastProfitTime": "1695371160000",  
                "historysByDateList": [  
                    {  
                        "profit": "2.40377986",  
                        "profitTime": "1695371100000"  
                    },  
                    {  
                        "profit": "0.01625000",  
                        "profitTime": "1693556100000"  
                    },  
                    {  
                        "profit": "2.16373741",  
                        "profitTime": "1693536000000"  
                    }  
                ]  
            }  
        ]  
    }  
}
```

### Response Description[​](#response-description "Direct link to Response Description")

| Parameter | Parameter Type | Description |
| --- | --- | --- |
| profitSummarys | Object | Elite trader profit share overview |
| >yesterdayProfit | String | Yesterday's profit share (elite traders) |
| >yesterdayTime | String | Yesterday's profit sharing time (milliseconds) |
| >sumProfit | String | Profit share in total |
| >waitProfit | String | To be shared |
| profitHistoryList | List | Profit list |
| >coin | String | Settlement currency (in cryptocurrency) |
| >profitCount | String | Profit overview (in cryptocurrency) |
| >lastProfitTime | String | The last time to distribute profit share (milliseconds) (in cryptocurrency) |
| >historysByDateList | List | Historical profit share overview (in the dimension of the cryptocurrency and the date) |
| >>profit | String | PnL (in the dimension of the cryptocurrency and the date) |
| >>profitTime | String | Time to distribute profit share (milliseconds) (in the dimension of the cryptocurrency and the date) |