# Cross Repay

Frequency limit: 10 times/1s (UID)

### Description[​](#description "Direct link to Description")

Repay

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/margin/crossed/account/repay

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/margin/crossed/account/repay" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*******" \  
   -H "ACCESS-PASSPHRASE:*****" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json" \     
   -d '{"coin": "BTC", "repayAmount":"0.1"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| coin | String | Yes | Repayment coin |
| repayAmount | String | Yes | Number of repayments (up to 8 decimal places) |

Response Example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1695636742119,  
  "data": {  
    "coin": "USDT",  
    "repayId": "12313123213",  
    "remainDebtAmount": "0.2",  
    "repayAmount": "0.1"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| remainDebtAmount | String | Remaining borrowings |
| repayId | String | repay ID |
| coin | String | Coin |
| repayAmount | String | Repayment amount |