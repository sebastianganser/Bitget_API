# Get Loan History

Frequency limit: 10c/1s (UID)

### Description[​](#description "Direct link to Description")

Get the list of loan history

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/earn/loan/borrow-history

Request Example

```json
curl "https://api.bitget.com/api/v2/earn/loan/borrow-history?startTime=1685957902000&endTime=1691228302423" \  
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
| status | String | No | Status `ROLLBACK`: failure `FORCE`: force liquidation `REPAY`: already repaid |
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
    "initPledgeAmount": "0.757",  
    "initLoanAmount": "4321321.23820848",  
    "hourRate": "59.1",  
    "daily": "7",  
    "borrowTime": "1684747528424",  
    "status": "REPAY"  
  }, {  
    "orderId": "12121212121",  
    "loanCoin": "TRX",  
    "pledgeCoin": "USDT",  
    "initPledgeAmount": "0.757",  
    "initLoanAmount": "4321321.23820848",  
    "hourRate": "59.1",  
    "daily": "7",  
    "borrowTime": "1684747528424",  
    "status": "REPAY"  
  }]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| loanCoin | String | Loan coin |
| pledgeCoin | String | Pledge (Collateral) coin |
| orderId | String | Order ID |
| initPledgeAmount | String | Initial pledge amount |
| initLoanAmount | String | Initial loan amount |
| hourRate | String | hourly rate percentage |
| daily | String | Pledge days |
| borrowTime | String | Borrowed time |
| status | String | Status `ROLLBACK`: failure `FORCE`: force liquidation `REPAY`: already repaid |