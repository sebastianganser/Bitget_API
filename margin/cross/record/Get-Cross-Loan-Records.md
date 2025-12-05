# Get Cross Borrow History

Frequency limit:10 times/1s (UID)

### Description[​](#description "Direct link to Description")

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/margin/crossed/borrow-history

Request Example

```json
curl "https://api.bitget.com/api/v2/margin/crossed/borrow-history?limit=20&startTime=1693205171000&endTime=1694155571000" \  
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
| loanId | String | No | Borrowing ID (exact match of single item) |
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
    "requestTime": 1695636829522,  
    "data": {  
        "resultList": [  
            {  
                "loanId": "1",  
                "coin": "USDT",  
                "borrowAmount": "12.1",  
                "borrowType": "manual_loan",  
                "cTime": "1695629859821",  
                "uTime": "1695629890839"  
            }  
        ],  
        "maxId": "1",  
        "minId": "1"  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| loanId | String | ID |
| coin | String | Borrowed coin |
| borrowAmount | String | Borrowing amount |
| borrowType | String | Type of borrowing `auto_loan`: auto borrow `manual_loan`: manual borrow |
| cTime | String | Creation time, millisecond timestamp |
| uTime | String | Update time, millisecond timestamp |