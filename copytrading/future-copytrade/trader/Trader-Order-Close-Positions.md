# Close Tracking Order

Rate Limit: 5 req/sec/UID

### Description[​](#description "Direct link to Description")

Tracking orders could only be closed by this API

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/copy/mix-trader/order-close-positions

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/copy/mix-trader/order-close-positions" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*******" \  
  -H "ACCESS-PASSPHRASE:*****" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json" \  
  -d '{"symbol": "BTCUSDT","productType": "usdt-futures","trackingNo": "1"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| trackingNo | String | No | Track order number  Tracking ID from the current elite trade interface If a symbol is also passed, make sure the order ID pair corresponds to it. |
| symbol | String | No | Trading pair Supports capital and lower-case letters |
| productType | String | Yes | Product type `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures If only productType is passed, all positions under that line of business will be closed. |

Response example

```json
{  
    "code": "00000",  
    "data": [  
        {  
            "trackingNo": "123",  
            "symbol": "ETHUSDT",  
            "productType": "USDT-FUTURES"  
        },  
        {  
            "trackingNo": "32123",  
            "symbol": "BTCUSDT",  
            "productType": "USDT-FUTURES"  
        }  
    ],  
    "msg": "success",  
    "requestTime": 1627354109502  
}
```

### Response parameters[​](#response-parameters "Direct link to Response parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| >trackingNo | String | Track order number |
| >symbol | String | Trading pair |
| >productType | String | Product type |