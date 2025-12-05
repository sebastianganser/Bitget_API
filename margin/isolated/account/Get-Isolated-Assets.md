# Get Isolated Account Asset

Frequency limit: 10 times/1s (UID)

### Description[​](#description "Direct link to Description")

Getting account asset

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/margin/isolated/account/assets

Request Example

```json
curl "https://api.bitget.com/api/v2/margin/isolated/account/assets?symbol=BTCUSDT" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*******" \  
   -H "ACCESS-PASSPHRASE:*****" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| symbol | String | No | Trading pairs, like BTCUSDT |

Response Example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1694588056713,  
  "data": [  
    {  
      "symbol": "BTCUSDT",  
      "coin": "BTC",  
      "totalAmount": "19876.1798394",  
      "available": "19876.1798394",  
      "frozen": "0",  
      "borrow": "0",  
      "interest": "0",  
      "net": "19876.1798394",  
      "coupon": "0",  
      "cTime": "1692085312298",  
      "uTime": "1694569802151"  
    }  
  ]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| coin | String | Token name |
| symbol | String | Trading pair name |
| totalAmount | String | Total amount |
| available | String | Available amount |
| frozen | String | Assets frozen |
| borrow | String | Borrow |
| interest | String | Interest, Interest-only payments with a minimum payment of interest. |
| net | String | Net assets = available + frozen − borrow − interest. Liquidation is triggered when the risk ratio is reached 1. |
| coupon | String | Trading bonus |
| cTime | String | Creation time |
| uTime | String | Update time |