# Get Repay History

Frequency limit: 10c/1s (UID)

### Description[​](#description "Direct link to Description")

Get the list of repay history

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/earn/loan/repay-history

Request Example

```json
curl "https://api.bitget.com/api/v2/earn/loan/repay-history?startTime=1685957902000&endTime=1691228302423" \  
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
| orderId | String | No | Order ID |
| loanCoin | String | No | Loan coin |
| pledgeCoin | String | No | Pledge (Collateral) coin |
| startTime | String | Yes | Start time, ms, only supports querying the data of the past three months |
| endTime | String | Yes | End time, ms |
| pageNo | String | No | Page No default 1 |
| pageSize | String | No | Page size default 10，max 100 |

Response example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1684747525424,  
  "data": [{  
    "orderId": "12121212121",  
    "loanCoin": "TRX",  
    "pledgeCoin": "USDT",  
    "repayAmount": "1566.23820848",  
    "payInterest": "0.1185634",  
    "repayLoanAmount": "1566.22635214",  
    "repayUnlockAmount": "195",  
    "repayTime": "1684747525424"  
  }, {  
    "orderId": "12121212121",  
    "loanCoin": "TRX",  
    "pledgeCoin": "USDT",  
    "repayAmount": "1566.23820848",  
    "payInterest": "0.1185634",  
    "repayLoanAmount": "1566.22635214",  
    "repayUnlockAmount": "195",  
    "repayTime": "1684747525424"  
  }]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| orderId | String | Order ID |
| loanCoin | String | Coin to loan |
| loanAmount | String | Pledge (Collateral) coin |
| repayAmount | String | Repay amount |
| payInterest | String | Paid interest |
| repayLoanAmount | String | Loan Currency Repayment of Principal Amount |
| repayUnlockAmount | String | Pledge (Collateral) release amount |
| repayTime | String | Repayment time |