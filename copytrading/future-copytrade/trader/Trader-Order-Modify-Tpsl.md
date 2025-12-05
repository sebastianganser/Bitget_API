# Modify Tracking Order TPSL

Rate Limit: 5 req/sec/UID

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/copy/mix-trader/order-modify-tpsl

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/copy/mix-trader/order-modify-tpsl" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*******" \  
  -H "ACCESS-PASSPHRASE:*****" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json" \  
  -d '{"symbol": "BTCUSDT","productType": "usdt-futures","trackingNo": "1","stopSurplusPrice":"36333","stopLossPrice":"29799"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| trackingNo | String | Yes | Elite trade order ID |
| productType | String | Yes | Product type `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures |
| stopSurplusPrice | String | No | TP price One of stopSurplusPrice and stopLossPrice must be passed. When it is empty, it is ignored or not updated, no matter take-profit exists or not, When it is 0, it means the original take-profit is canceled if there is a take-profit already. When it is greater than or equal to 0, it means take-profit is updated or set. |
| stopLossPrice | String | No | SL price One of stopSurplusPrice and stopLossPrice must be passed. When it is empty, it is ignored or not updated, no matter stop-loss exists or not, When it is 0, it means the original stop-loss is canceled if there is a stop-loss already. When it is greater than or equal to 0, it means stop-loss is updated or set. |

Response example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1656066841304,  
    "data": "success"  
}
```

### Response parameters[​](#response-parameters "Direct link to Response parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| data | String | Implementation results `success` `fail` |