# Get Pledge Rate History

Frequency limit: 10c/1s (UID)

### Description[​](#description "Direct link to Description")

Get pledge rate history

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/earn/loan/revise-history

Request Example

```json
curl "https://api.bitget.com/api/v2/earn/loan/revise-history?startTime=1685957902000&endTime=1691228302423" \  
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
| reviseSide | String | No | Revise side `down`: supplement collateral to turn down `up`: withdraw collateral to turn up |
| pledgeCoin | String | No | Pledge (Collateral) coin |
| startTime | String | Yes | Start time, ms, only supports querying the data of the past three months |
| endTime | String | Yes | End time, ms |
| pageNo | String | No | pageNo default 1 |
| pageSize | String | No | pageSize default 10，max 100 |

Response example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1692436125845,  
  "data": [  
    {  
      "loanCoin": "ETH",  
      "pledgeCoin": "USDT",  
      "orderId": "1",  
      "reviseTime": "1692436102448",  
      "reviseSide": "down",  
      "reviseAmount": "10",  
      "afterPledgeRate": "64.75",  
      "beforePledgeRate": "65"  
    }  
  ]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| loanCoin | String | Loan coin |
| pledgeCoin | String | Pledge (Collateral) coin |
| orderId | String | Order ID |
| reviseTime | String | Adjust time |
| reviseSide | String | Revise side `down`: supplement collateral to turn down `up`: withdraw collateral to turn up |
| reviseAmount | String | Adjustment quantity |
| afterPledgeRate | String | Pledge Rate Percentage after adjustment |
| beforePledgeRate | String | Pledge rate percentage before adjustment |