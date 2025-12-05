# Get Isolated Max Borrowable

Frequency limit: 10 times/1s (UID)

### Description[​](#description "Direct link to Description")

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/margin/isolated/account/max-borrowable-amount

Request Example

```json
curl "https://api.bitget.com/api/v2/margin/isolated/account/max-borrowable-amount?symbol=BTCUSDT" \  
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
| symbol | String | Yes | Trading pairs, like BTCUSDT |

Response Example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1695636742119,  
  "data": {  
    "symbol": "ETHUSDT",  
    "baseCoin": "ETH",  
    "baseCoinMaxBorrowAmount": "10.1401916",  
    "quoteCoin": "USDT",  
    "quoteCoinMaxBorrowAmount": "3976070.21616"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| symbol | String | Trading pair |
| baseCoin | String | Left coin |
| baseCoinMaxBorrowAmount | String | Maximum borrow amount of left coins (amount changes in real time) |
| quoteCoin | String | Right coin |
| quoteCoinMaxBorrowAmount | String | Maximum borrow amount of right coins |