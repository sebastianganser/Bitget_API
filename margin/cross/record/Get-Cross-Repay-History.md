# Get Cross Repay History

Frequency limit:10 times/1s (IP)

### Description[​](#description "Direct link to Description")

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/margin/crossed/repay-history

Request Example

```json
curl "https://api.bitget.com/api/v2/margin/crossed/repay-history?limit=20&startTime=1693205171000&endTime=1694155571000" \  
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
| repayId | String | No | Repayment ID |
| coin | String | No | Coin |
| startTime | String | Yes | Start time, Unix millisecond timestamp |
| endTime | String | No | End time, Unix millisecond timestamp Maximum interval between start time and end time is 90 days |
| limit | String | No | Number of quiries Default: 100, maximum: 500 |
| idLessThan | String | No | For turning pages. The first query is not passed. When querying data in the second page and the data beyond, the last repayId returned in the last query is used, and the result will return data with a value less than this one; the query response time will be shortened. |

Response Example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1695636829522,  
    "data": {  
        "resultList": [  
            {  
                "repayId": "1",  
                "coin": "USDT",  
                "repayAmount": "12.1",  
                "repayType": "manual_repay",  
                "repayInterest": "0.0001",  
                "repayPrincipal": "0.1",  
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
| repayId | String | Repayment ID |
| coin | String | Repayment coin |
| repayPrincipal | String | Repayment principal |
| repayAmount | String | Total repayment |
| repayInterest | String | Repayment interest |
| repayType | String | Repayment type auto\_repay automatic repayment manual\_repay manual repayment liq\_repay liquidate and repay force\_repay compulsory repayment |
| cTime | String | Creation time, millisecond timestamp |
| uTime | String | Update time, millisecond timestamp |