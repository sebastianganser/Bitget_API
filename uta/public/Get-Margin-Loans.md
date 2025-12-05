# Get Margin Loan

### Description[​](#description "Direct link to Description")

Query interest rates for margin loans.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/market/margin-loans
* Rate limit: 20/sec/IP

Request

```json
curl "https://api.bitget.com/api/v3/market/margin-loans?coin=BTC"  \
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| coin | String | Yes | Coin name e.g.,`BTC` |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1730912814587,  
  "data": {  
    "dailyInterest": "0.1",  
    "annualInterest": "0.00416667",  
    "limit": "3000"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| dailyInterest | String | Daily interest rate |
| annualInterest | String | Annual interest rate |
| limit | String | Loan limit |