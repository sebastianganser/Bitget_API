# Get Cross Account Assets

Frequency limit: 10 times/1s (UID)

### Description[​](#description "Direct link to Description")

Getting account asset

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/margin/crossed/account/assets

Request Example

```json
curl "https://api.bitget.com/api/v2/margin/crossed/account/assets?coin=USDT" \  
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
| coin | String | No | Coin, like USDT |

Response Example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1695636742119,  
  "data": [{  
    "coin": "USDT",  
    "totalAmount": "12",  
    "available": "2",  
    "frozen": "0",  
    "borrow": "0.1",  
    "interest": "0.000001",  
    "net": "0.1",  
    "cTime":"1734567744432",  
    "uTime":"1734567744432",  
    "coupon": "0"  
  }]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| coin | String | Token name |
| totalAmount | String | Total amount |
| available | String | Available amount |
| frozen | String | Assets frozen |
| borrow | String | Borrow |
| interest | String | Interest, Interest-only payments with a minimum payment of interest. |
| net | String | Net assets = available + frozen − borrow − interest. Liquidation is triggered when the Maintenance Margin Ratio (MMR) is reached. |
| coupon | String | Trading bonus |
| cTime | String | Creation time |
| uTime | String | Update time |