# Modify Pledge Rate

Frequency limit: 10c/1s (UID)

### Description[​](#description "Direct link to Description")

Withdraw or supplement collateral

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/earn/loan/revise-pledge

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/earn/loan/revise-pledge" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*******" \  
  -H "ACCESS-PASSPHRASE:*****" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json" \  
 -d '{  
    "orderId":"1",  
    "pledgeCoin":"USDT",  
    "reviseType":"OUT",  
    "amount":"1"  
}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| orderId | String | Yes | Order ID |
| amount | String | Yes | Amount to withdraw or supplement |
| pledgeCoin | String | Yes | Pledge (Collateral) coin |
| reviseType | String | Yes | Repay Type `OUT`: Withdraw collateral `IN` supplement collateral |

Response example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1684747525424,  
  "data": {  
    "loanCoin": "TRX",  
    "pledgeCoin": "USDT",  
    "afterPledgeRate": "60.5"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| loanCoin | Loan coin |  |
| pledgeCoin | Pledge (Collateral) coin |  |
| afterPledgeRate | Pledge Rate Percentage after adjusted |  |