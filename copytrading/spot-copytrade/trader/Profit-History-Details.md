# Get History Profit Sharing Details

Rate Limit: 5 req/sec/UID

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/copy/spot-trader/profit-history-details

Request Example

```json
curl "https://api.bitget.com/api/v2/copy/spot-trader/profit-history-details" \  
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
| idLessThan | String | No | Request the paging content before this ID (older data), and the passed value is the endId of the corresponding interface. |
| idGreaterThan | String | No | Request the paging content after this ID (updated data). The value passed is the endId of the corresponding interface. |
| startTime | String | No | start time |
| endTime | String | No | end time |
| limit | String | No | Number of queries: Default 100, maximum 100 |
| coin | String | No | Profit sharing settlement currency |

Response example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1695806800430,  
    "data": {  
        "endId": "4",  
        "profitList": [  
            {  
                "profitId": "1",  
                "coin": "USDT",  
                "distributeRatio": "8",  
                "profit": "2.40377986",  
                "followerName": "xx1",  
                "profitTime": "1695371100000"  
            },  
            {  
                "profitId": "2",  
                "coin": "USDT",  
                "distributeRatio": "8",  
                "profit": "0.00000000",  
                "followerName": "xx2",  
                "profitTime": "1693822200000"  
            },  
            {  
                "profitId": "3",  
                "coin": "USDT",  
                "distributeRatio": "8",  
                "profit": "0.01625000",  
                "followerName": "xx3",  
                "profitTime": "1693556100000"  
            },  
            {  
                "profitId": "4",  
                "coin": "USDT",  
                "distributeRatio": "8",  
                "profit": "2.16373741",  
                "followerName": "xx4",  
                "profitTime": "1693536000000"  
            }  
        ]  
    }  
}
```

### Response Description[​](#response-description "Direct link to Response Description")

| Parameter | Parameter Type | Description |
| --- | --- | --- |
| profitList | List | Profit share overview |
| >profitId | String | Profit share ID |
| >coin | String | Settlement currency |
| >distributeRatio | String | Profit share ratio  If the value is 11.11, it represents 11.11% |
| >profit | String | PnL |
| >followerName | String | Elite trader alias |
| >profitTime | String | Time to distribute profit share |
| endId | String | The last profit share ID. This is used when idLessThan/idGreaterThan is set as the querying scope. |