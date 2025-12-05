# Get Loan Orders

Frequency limit: 10c/1s (UID)

### Description[​](#description "Direct link to Description")

Get on-going loan orders

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/earn/loan/ongoing-orders

Request Example

```json
curl "https://api.bitget.com/api/v2/earn/loan/ongoing-orders?orderId=1" \  
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
| loanCoin | String | No | Coin to loan |
| pledgeCoin | String | No | Pledge (Collateral) coin |

Response example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1692434611622,  
  "data": [  
    {  
      "orderId": "1",  
      "loanCoin": "ETH",  
      "loanAmount": "1",  
      "interestAmount": "0.00000229",  
      "hourInterestRate": "0.000229",  
      "pledgeCoin": "USDT",  
      "pledgeAmount": "2619.69231032",  
      "pledgeRate": "65",  
      "supRate": "75",  
      "forceRate": "83",  
      "borrowTime": "1692434472156",  
      "expireTime": "1693036799999"  
    }  
  ]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| orderId | String | Order ID |
| loanCoin | String | Coin to loan |
| loanAmount | String | Loan amount |
| interestAmount | String | Interest amount |
| hourInterestRate | String | Hour interest rate |
| pledgeCoin | String | Pledge (Collateral) coin |
| pledgeAmount | String | Pledge (Collateral) amount |
| pledgeRate | String | Pledge (Collateral) rate |
| supRate | String | Supplementary rate |
| forceRate | String | Forced Liquidation Pledge Rate Percentage |
| borrowTime | String | Borrow time millseconds |
| expireTime | String | Expire time millseconds |