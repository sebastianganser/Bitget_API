# Get Cross Max Borrowable

Frequency limit: 10 times/1s (UID)

### Description[​](#description "Direct link to Description")

Get max borrowable

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/margin/crossed/account/max-borrowable-amount

Request Example

```json
curl "https://api.bitget.com/api/v2/margin/crossed/account/max-borrowable-amount?coin=USDT" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*******" \  
   -H "ACCESS-PASSPHRASE:*****" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json" \
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| coin | String | Yes | Borrowing coins, such as BTC |

Response Example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1695636742119,  
  "data": {  
    "coin": "USDT",  
    "maxBorrowableAmount": "3976070.21616"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| maxBorrowableAmount | String | Maximum borrow amount (amount changes in real time) |
| coin | String | Coin |