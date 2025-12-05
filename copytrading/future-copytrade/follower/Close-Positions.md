# Close Positions

Rate Limit: 5 req/sec/UID

Interface for followers to close positions. Can close positions based on order ID, trading pair, direction, position mode, and margin

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/copy/mix-follower/close-positions

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/copy/mix-follower/close-positions" \  
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
| productType | String | Yes | Product type `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures |
| trackingNo | String | No | Tracking numbers of buying orders grouped by trading pair （If you pass the trackingNo and ensure that the symbol, marginCoin, marginMode, and holdSide are not empty, you need to ensure that the trackingNo corresponds to them.） |
| symbol | String | No | Trading pair |
| marginCoin | String | No | margin coin |
| marginMode | String | No | Position mode `isolated`: isolated margin  `cross`: cross margin |
| holdSide | String | No | Position direction  1. In the buying and selling (one-way position) mode: you don’t have to fill it in, if you fill it in, it will be ignored.  2. In the opening and closing position (hedge mode): This parameter must be filled in.  `long`: long position in hedging mode `short`: short position in hedging mode |

Response example

```json
{  
    "code": "00000",  
    "data": {  
        "orderIdList": [  
            "123",  
            "321"  
        ]  
    },  
    "msg": "success",  
    "requestTime": 1627293504612  
}
```

### Response parameters[​](#response-parameters "Direct link to Response parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| orderIdList | List<String> | Order ID |