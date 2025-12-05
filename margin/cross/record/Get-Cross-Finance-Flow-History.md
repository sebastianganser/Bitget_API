# Get Cross Financial History

Frequency limit:10 times/1s (UID)

### Description[​](#description "Direct link to Description")

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/margin/crossed/financial-records

Request Example

```json
curl "https://api.bitget.com/api/v2/margin/crossed/financial-record?coin=USDT&limit=20&startTime=1693205171000&endTime=1694155571000" \  
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
| marginType | String | No | Capital flow type transfer\_in: assets transferred in transfer\_out: assets transferred out borrow: borrow repay: repay liquidation\_fee: liquidation fee compensate: collateral shortfall compensation from risk fund deal\_in: trade and deposit (buy) deal\_out: trade and withdraw (sell) confiscated: deduction for collateral shortfall exchange\_in: exchange income, charged from the system account exchange\_out: exchange expense, charged to the system account sys\_exchange\_in: exchange income of the system account, with exchange expense appearing at the same time sys\_exchange\_out: exchange expense of the system account, with exchange income appearing at the same time |
| coin | String | No | Coin |
| startTime | String | Yes | Start time, Unix millisecond timestamp |
| endTime | String | No | End time, Unix millisecond timestamp Maximum interval between start time and end time is 90 days |
| limit | String | No | Number of quiries Default: 100, maximum: 500 |
| idLessThan | String | No | For turning pages. The first query is not passed. When querying data in the second page and the data beyond, the last marginId returned in the last query is used, and the result will return data with a value less than this one; the query response time will be shortened. |

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
                "marginId": "1",  
                "amount": "10.12",  
                "coin": "USDT",  
                "balance": "156",  
                "fee": "0",  
                "marginType": "transfer_in",  
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
| coin | String | Coin |
| marginId | String | Capital flow ID |
| marginType | String | Capital flow type transfer\_in: assets transferred in transfer\_out: assets transferred out borrow: borrow repay: repay liquidation\_fee: liquidation fee compensate: collateral shortfall compensation from risk fund deal\_in: trade and deposit (buy) deal\_out: trade and withdraw (sell) confiscated: deduction for collateral shortfall exchange\_in: exchange income, charged from the system account exchange\_out: exchange expense, charged to the system account sys\_exchange\_in: exchange income of the system account, with exchange expense appearing at the same time sys\_exchange\_out: exchange expense of the system account, with exchange income appearing at the same time |
| amount | String | Capital flow amount |
| balance | String | Account balance |
| fee | String | Transaction fee details |
| cTime | String | Creation time, millisecond timestamp |
| uTime | String | Update time, millisecond timestamp |