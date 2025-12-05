# Get Loan Orders

### Description[​](#description "Direct link to Description")

Get Loan Orders

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/ins-loan/loan-order
* Rate limit: 3/sec/UID
* Permission: UTA mgt. (read)

Request

```json
curl "https://api.bitget.com/api/v3/ins-loan/loan-order?orderId=xxxxxxxx" \  
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
| orderId | String | No | oan order id. If not passed, then return all orders, sort by `loanTime` in descend |
| startTime | String | No | The start timestamp (ms) |
| endTime | String | No | The end timestamp (ms) |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1711697588556,  
  "data": [  
    {  
      "orderId": "xxxxxxx",  
      "orderProductId": "xxxxxx",  
      "uid": "xxxxxx",  
      "loanTime": "1713645576789",  
      "loanCoin": "USDT",  
      "loanAmount": "8400",  
      "unpaidAmount": "8400",  
      "unpaidInterest": "0",  
      "repaidAmount": "1",  
      "repaidInterest": "1.1",  
      "reserve": "168",  
      "status": "not_paid_off"  
    }  
  ]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| loanInfo | Array | Loan details |
| > orderId | String | Loan order ID |
| > orderProductId | String | Product Id |
| > uid | String | The designated UID that is used to bind INS loan product, loan and repayment |
| > loanTime | String | Loan timestamp, in milliseconds |
| > loanCoin | String | Loan coin |
| > loanAmount | String | Loan amount |
| > unpaidAmount | String | Unpaid principal |
| > unpaidInterest | String | Unpaid interest |
| > repaidAmount | String | Repaid principal |
| > repaidInterest | String | Repaid interest |
| > reserve | String | reserve amount |
| > status | String | Not paid off `not_paid_off`;  Paid off `paid_off` |