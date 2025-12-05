# Get Liquidation Records

Frequency limit: 10c/1s (UID)

### Description[​](#description "Direct link to Description")

Get the list of repay history

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/earn/loan/reduces

Request Example

```json
curl "https://api.bitget.com/api/v2/earn/loan/reduces?startTime=1685957902000&endTime=1691228302423" \  
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
| status | String | No | Status `COMPLETE` completed liquidation `WAIT` liquidating |
| startTime | String | Yes | Start time, ms, only supports querying the data of the past three months |
| endTime | String | Yes | End time, ms |
| pageNo | String | No | Page No, default 1 |
| pageSize | String | No | Page size, default 10, max 100 |

Response example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1684747525424,  
  "data": [{  
    "orderId": "1",  
    "loanCoin": "TRX",  
    "pledgeCoin": "USDT",  
    "reduceTime": "0.757",  
    "pledgeRate": "98.2",  
    "pledgePrice": "111.4",  
    "status": "COMPLETE",  
    "pledgeAmount": "1213.5",  
    "reduceFee": "REPAY",  
    "residueAmount": "3234.2",  
    "runlockAmount": "23",  
    "repayLoanAmount": "53.2"  
  }, {  
    "orderId": "12121212121",  
    "loanCoin": "TRX",  
    "pledgeCoin": "USDT",  
    "reduceTime": "0.757",  
    "pledgeRate": "98.2",  
    "pledgePrice": "111.4",  
    "status": "COMPLETE",  
    "pledgeAmount": "1213.5",  
    "reduceFee": "REPAY",  
    "residueAmount": "3234.2",  
    "runlockAmount": "23",  
    "repayLoanAmount": "53.2"  
  }]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| orderId | String | Order ID |
| loanCoin | String | Loan coin |
| pledgeCoin | String | Pledge (Collateral) coin |
| reduceTime | String | Liquidated time |
| pledgeRate | String | Pledge percentage during liquidation |
| pledgePrice | String | Pledge price when Liquidated |
| status | String | Status `COMPLETE` liquidation completed `WAIT` liquidating |
| pledgeAmount | String | Liquidation amount of pledged coin |
| reduceFee | String | Liquidation fee |
| residueAmount | String | Remaining pledged amount |
| runlockAmount | String | Released amount of pledged coin |
| repayLoanAmount | String | Repayment amount of the loan |