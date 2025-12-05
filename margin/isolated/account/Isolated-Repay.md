# Isolated Repay

Frequency limit: 10 times/1s (UID)

### Description[​](#description "Direct link to Description")

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/margin/isolated/account/repay

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/margin/isolated/account/repay" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*******" \  
   -H "ACCESS-PASSPHRASE:*****" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json"  -d '{"coin": "USDT","repayAmount": "1","symbol":"BTCUSDT"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| repayAmount | String | Yes | Number of repayments, up to 8 decimal places |
| coin | String | Yes | Repayment coin |
| symbol | String | Yes | Repayment trading pairs, like BTCUSDT |
| clientOid | String | No | Client customized ID |

Response Example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1694588859956,  
  "data": {  
    "remainDebtAmount": "0",  
    "symbol": "BTCUSDT",  
    "repayId":"1234234234234",  
    "coin": "USDT",  
    "repayAmount": "1"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| remainDebtAmount | String | Remaining borrowings |
| repayId | String | Repayment ID |
| symbol | String | Trading pair |
| coin | String | Coin |
| repayAmount | String | Repayment amount |