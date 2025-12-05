# Get History Profit Share Detail

Rate Limit: 5 req/sec/UID

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/copy/mix-trader/profit-history-details

Request Example

```json
curl "https://api.bitget.com/api/v2/copy/mix-trader/profit-history-details?coin=USDT&limit=20&startTime=1693205171000&endTime=1694155571000" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*******" \  
  -H "ACCESS-PASSPHRASE:*****" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| coin | String | No | Settlement currency |
| idLessThan | String | No | Separate page content before this ID is requested (older data), and the value input should be the endid of the corresponding interface. |
| idGreaterThan | String | No | Separate page content after this ID is requested (newer data), and the value input should be the endid of the corresponding interface. |
| startTime | String | No | Start timestamp  Milliseconds format of timestamp Unix, e.g. 1597026383085 (The maximum time span supported is three months. The default end time is three months if no value is set for the end time. ) |
| endTime | String | No | End timestamp  Milliseconds format of timestamp Unix, e.g. 1597026383085 (The maximum time span supported is three months. The default start time is three months ago if no value is set for the start time. ) |
| limit | String | No | Number of queries: Default: 100, maximum: 100 |

Response example

```json
{  
    "code": "00000",  
    "data": {  
        "profitList": [  
            {  
                "profitId": "1",  
                "coin": "usdt",  
                "profit": "1",  
                "nickName": "nickname",  
                "profitTime": "1691446639000"  
            }  
        ],  
        "endId": "3"  
    },  
    "msg": "success",  
    "requestTime": 1627354109502  
}
```

### Response parameters[​](#response-parameters "Direct link to Response parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| profitList | List | profit share overview |
| >profitId | String | Profit share ID |
| >coin | String | Settlement currency |
| >profit | String | Distributed |
| >nickName | String | Alias |
| >profitTime | String | Time to distribute profit share |
| endId | String | The last profit share ID. This is used when idLessThan/idGreaterThan is set as a range. |