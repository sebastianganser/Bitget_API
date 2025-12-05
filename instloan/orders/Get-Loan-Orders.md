# Get Loan Orders

Rate limit: 5 req/sec/UID

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/spot/ins-loan/loan-order

Request Example

```json
curl "https://api.bitget.com/api/api/v2/spot/ins-loan/loan-order" \  
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
| orderId | String | No | Loan order id If not passed, then return all orders, sort by loanTime in descend |
| startTime | String | No | The start timestamp (ms)   （The maximum time span supported is 30 days. If the start time is not provided, it defaults to the current time minus 30 days.） |
| endTime | String | No | The end timestamp (ms)   （The maximum time span supported is 30 days. If the end time is not provided, the default end time is 30 days from the start.） |

Response Example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1711697588556,  
  "data": [{  
    "orderId": "xxxxxxx",  
    "orderProductId": "xxxxxx",  
    "uid":"xxxxxx",  
    "loanTime":"1713645576789",  
    "loanCoin":"USDT",  
    "unpaidAmount":"1",  
    "unpaidInterest":"1",  
    "loanAmount":"1",  
    "status":"paid_off",  
    "repaidAmount":"1",  
    "repaidInterest":"1.1"  
  }]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| loanInfo | Array | Loan orders information |
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
| > status | String | Status `not_paid_off`: Not paid off `paid_off`: paid off |