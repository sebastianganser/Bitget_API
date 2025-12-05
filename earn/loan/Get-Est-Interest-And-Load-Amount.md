# Get Est. Interest and Borrowable

Frequency limit: 10c/1s (IP)

### Description[​](#description "Direct link to Description")

Get Est. hourly interest rate and Borrowable amount

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/earn/loan/public/hour-interest

Request Example

```json
curl "https://api.bitget.com/api/v2/earn/loan/public/hour-interest?loanCoin=USDT&pledgeCoin=ETH&pledgeAmount=0.2&daily=SEVEN" \  
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
| loanCoin | String | Yes | Coin to loan, `BTC` |
| pledgeCoin | String | Yes | Collateral coin, `ETH` |
| daily | String | Yes | Mortgage term `SEVEN`: 7 days `THIRTY`: 30 days  `FLEXIBLE`: Flexible |
| pledgeAmount | String | Yes | Pledge amount |

Response example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1692433739845,  
  "data": {  
    "hourInterest": "0.00133436",  
    "loanAmount": "216.2654"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| hourInterest | String | Estimated interest amount per hour |
| loanAmount | String | Borrowable amount |