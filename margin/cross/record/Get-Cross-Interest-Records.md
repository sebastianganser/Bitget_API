# Get Cross Interest History

Frequency limit:10 times/1s (UID)

### Description[​](#description "Direct link to Description")

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/margin/crossed/interest-history

Request Example

```json
curl "https://api.bitget.com/api/v2/margin/crossed/interest-history?coin=USDT&limit=20&startTime=1693205171000&endTime=1694155571000" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*******" \  
   -H "ACCESS-PASSPHRASE:*****" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json" \
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| coin | String | No | Coin |
| startTime | String | Yes | Start time, Unix millisecond timestamp |
| endTime | String | No | End time, Unix millisecond timestamp Maximum interval between start time and end time is 90 days |
| limit | String | No | Number of quiries Default: 100, maximum: 500 |
| idLessThan | String | No | For turning pages. The first query is not passed. When querying data in the second page and the data beyond, the last loanId returned in the last query is used, and the result will return data with a value less than this one; the query response time will be shortened. |

Response Example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1668134626684,  
    "data": {  
        "minId": "1",  
        "maxId": "1",  
        "resultList": [  
            {  
                "interestId": "1",  
                "loanCoin": "USDT",  
                "interestCoin": "USDT",  
                "dailyInterestRate": "0.00001",  
                "interestAmount": "1.2",  
                "interstType": "first",  
                "uTime": "1668134458717",  
                "cTime": "1668134458717"  
            }  
        ]  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| interestId | String | ID |
| interestAmount | String | Interest amount |
| dailyInterestRate | String | Daily interest rate |
| interstType | String | Interest type first interest on initial borrowing scheduled: scheduled interest |
| interestCoin | String | Interest coin |
| loanCoin | String | Borrowing coin |
| cTime | String | Creation time |
| uTime | String | Update time, millisecond timestamp |