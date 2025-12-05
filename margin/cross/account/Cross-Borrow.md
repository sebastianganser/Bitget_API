# Cross Borrow

Frequency limit: 10 times/1s (UID)

### Description[​](#description "Direct link to Description")

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/margin/crossed/account/borrow

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/margin/crossed/account/borrow"  -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*******" \  
   -H "ACCESS-PASSPHRASE:*****" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json"  -d '{"coin": "USDT","borrowAmount": "1"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| coin | String | Yes | Borrowing coin |
| borrowAmount | String | Yes | Borrowing amount (up to 8 decimal places) |
| clientOid | String | No | 客户自定义订单ID |

Response Example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1679384491703,  
  "data": {  
    "loanId": "2342332432",  
    "coin": "USDT",  
    "borrowAmount": "1.00000000"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| loanId | String | Loan order ID |
| coin | String | Borrowing coin |
| borrowAmount | String | Borrowing amount |