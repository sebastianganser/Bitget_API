# Set TPSL

Rate Limit: 5 req/sec/UID

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/copy/mix-follower/setting-tpsl

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/copy/mix-follower/setting-tpsl" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*******" \  
  -H "ACCESS-PASSPHRASE:*****" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json" \  
  -d '{"productType":"USDT-FUTURES","symbol":"BTCUSDT","trackingNo":"1","stopSurplusPrice":"37878"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| trackingNo | String | Yes | Order tracking number |
| symbol | String | No | Trading pair |
| productType | String | Yes | Product type `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures |
| stopSurplusPrice | String | No | Take profit price When it is empty, it is ignored or not updated, no matter take-profit exists or not, When it is 0, it means the original take-profit is canceled if there is a take-profit already. When it is greater than or equal to 0, it means take-profit is updated or set. |
| stopLossPrice | String | No | Stop loss price When it is empty, it is ignored or not updated, no matter stop-loss exists or not, When it is 0, it means the original stop-loss is canceled if there is a stop-loss already. When it is greater than or equal to 0, it means stop-loss is updated or set. |

Response example

```json
{  
    "code": "00000",  
    "data": "success",  
    "msg": "success",  
    "requestTime": 1627354109502  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| data | String | Result `success`: success,`fail`: fail |