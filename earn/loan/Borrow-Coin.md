# Borrow

Frequency limit: 10c/1s (UID)

### Description[​](#description "Direct link to Description")

Borrow coin

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/earn/loan/borrow

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/earn/loan/borrow" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*******" \  
  -H "ACCESS-PASSPHRASE:*****" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json" \  
 -d '{  
    "loanCoin":"ETH",  
    "pledgeCoin":"USDT",  
    "daily":"SEVEN",  
    "loanAmount":"0.01"  
}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| loanCoin | String | Yes | Coin to loan, `ETH` |
| pledgeCoin | String | Yes | Pledge coin (Collateral), `USDT` |
| daily | String | Yes | Mortgage term `SEVEN`: 7 days `THIRTY`: 30 days  `FLEXIBLE`: Flexible |
| pledgeAmount | String | No | Pledge (Collateral) amount, `pledgeAmount` and `loanAmount` must send one |
| loanAmount | String | No | Loan amount, `pledgeAmount` and `loanAmount` must send one |

Response example

```json
{  
  "code":"00000",  
  "msg":"success",  
  "requestTime":163123213132,  
  "data": {  
    "orderId": "1"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| orderId | String | Order ID |