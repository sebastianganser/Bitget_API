# Get Currency List

Frequency limit: 10c/1s (IP)

### Description[​](#description "Direct link to Description")

Get loan-able currency list

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/earn/loan/public/coinInfos

Request Example

```json
curl "https://api.bitget.com/api/v2/earn/loan/public/coinInfos" \  
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
| coin | String | No | Coin, `BTC` |

Response example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1692433281223,  
  "data": {  
    "loanInfos": [  
      {  
        "coin": "USDT",  
        "hourRate7D": "0.00000617",  
        "rate7D": "0.054",  
        "hourRate30D": "0.00000879",  
        "rate30D": "0.077",  
        "minUsdt": "200",  
        "maxUsdt": "1000000",  
        "min": "200",  
        "max": "1000000"  
      }  
  ],  
  "pledgeInfos": [  
    {  
      "coin": "MATIC",  
      "initRate": "0.6",  
      "supRate": "0.75",  
      "forceRate": "0.83",  
      "minUsdt": "0",  
      "maxUsdt": "200000"  
    }  
  ]  
  }   
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| loanInfos | String | Loan infos |
| >coin | String | Loan coin |
| >hourRate7D | String | 7 days fixed rate per hour percentage |
| >rate7D | String | 7-day fixed rate annualized percentage |
| >hourRate30D | String | 30-day fixed rate hourly percentage |
| >rate30D | String | 30-day fixed rate annualized percentage |
| >minUsdt | String | Minimum Borrowable limit usdt |
| >maxUsdt | String | Maximum borrowing limit usdt |
| >min | String | Minimum borrowing limit |
| >max | String | Maximum borrowing limit |
| pledgeInfos | String | Pledge infos |
| >coin | String | Pledge coin |
| >initRate | String | Initial pledge rate percentage |
| >supRate | String | Percentage of supplementary guarantee pledge rate |
| >forceRate | String | Forced Liquidation Pledge Rate Percentage |
| >minUsdt | String | Minimum pledge limit usdt |
| >maxUsdt | String | Maximum pledge limit usdt |