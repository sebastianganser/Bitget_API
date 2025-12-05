# Get Repayment Orders

### Description[​](#description "Direct link to Description")

Get Repayment Orders

* By default, query the data of the past two years.
* At most, support querying the data of the past two years.
* Only display the data of successfully repaid orders.
* Only display the repayment orders under the unified account. The orders under the spot account can be queried through
  the v2 version.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/ins-loan/repaid-history
* Rate limit: 3/sec/UID
* Permission: UTA mgt. (read)

Request

```json
curl "https://api.bitget.com/api/v3/ins-loan/repaid-history" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| startTime | String | No | The start timestamp (ms) |
| endTime | String | No | The end timestamp (ms) |
| limit | String | No | Limit default 100; max 100 |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1711697588556,  
  "data": [  
    {  
      "repayOrderId": "xxxxxxx",  
      "businessType": "liquidation",  
      "repayType": "part",  
      "repaidTime": "1745654869294",  
      "coin": "USDT",  
      "repayAmount": "5092.45423168",  
      "repayInterest": "0"  
    },  
    {  
      "repayOrderId": "xxxxxxx",  
      "businessType": "normal",  
      "repayType": "all",  
      "repaidTime": "1713645576789",  
      "coin": "USDT",  
      "repaidAmount": "1",  
      "repaidInterest": "1.1"  
    }  
  ]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| > repayOrderId | String | Repaid order ID |
| > repaidTime | String | Repaid timestamp (ms) |
| > coin | String | Repaid coin |
| > repayAmount | String | Repaid principle |
| > repayInterest | String | Repaid interest |
| > repayType | String | Repaid type: all: All repayment; part: partial repayment |
| > businessType | String | Business type: normal: normal repayment; liquidation: repaid by liquidation |