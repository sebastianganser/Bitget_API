# Repay

Frequency limit: 10c/1s (UID)

### Description[​](#description "Direct link to Description")

Repay

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/earn/loan/repay

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/earn/loan/repay" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*******" \  
  -H "ACCESS-PASSPHRASE:*****" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json" \  
 -d '{  
    "orderId":"ETH",  
    "repayAll":"yes",  
    "repayUnlock":"yes"  
}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| orderId | String | Yes | Order ID |
| amount | String | No | When `repayAll`=`no`: Repay amount |
| repayUnlock | String | No | Whether redeem after repay, default: `yes` `yes` `no` |
| repayAll | String | Yes | Repay all `yes` `no` |

Response example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1684747525424,  
  "data": {  
    "loanCoin": "TRX",  
    "pledgeCoin": "USDT",  
    "repayAmount": "1566.23820848",  
    "payInterest": "0.1185634",  
    "repayLoanAmount": "1566.22635214",  
    "repayUnlockAmount": "195"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| loanCoin | String | Coin to loan |
| pledgeCoin | String | Pledge (Collateral) coin |
| repayAmount | String | Repay amount |
| payInterest | String | Paid interest |
| repayLoanAmount | String | Repay loan amount |
| repayUnlockAmount | String | Pledge (Collateral) redeemed amount |