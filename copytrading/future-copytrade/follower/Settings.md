# Set Copy Trade Settings

Rate Limit: 5 req/sec/UID

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/copy/mix-follower/settings

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/copy/mix-follower/settings" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*******" \  
  -H "ACCESS-PASSPHRASE:*****" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json" \  
  -d '{"traderId":"123123123","settings":[{"symbol":"BTCUSDT","productType":"USDT-FUTURES","marginType":"trader","marginCoin":"USDT","leverType":"trader","traceType":"amount","traceValue":"330","maxHoldSize":"5000"}]}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| traderId | String | Yes | ID of the elite trader that you followed |
| autoCopy | String | No | Whether to automatically follow new symbol opened by traders(only take effect when parameter mode is basic)   on：auto   off：no |
| mode | String | No | follow mode   basic：basic mode   advanced（default）：advanced mode |
| settings | List | Yes | Settings of copy trading (based on trading pair) Maximum: 10 |
| >symbol | String | Yes | Trading pair |
| >productType | String | Yes | Product type `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures |
| >marginType | String | Yes | Margin type(only take effect when parameter mode is advanced) `trader` margin type of the elite trader that you followed; `specify` your own margin type. |
| >marginCoin | String | No | Margin currency |
| >leverType | String | Yes | Leverage type(only take effect when parameter mode is advanced) `position` use position leverage; `specify` use the specified leverage; `trader` use the leverage of the elite trader; |
| >longLeverage | String | No | Leverage of long positions (only take effect when parameter mode is advanced) |
| >shortLeverage | String | No | Leverage of short positions (only take effect when parameter mode is advanced) |
| >traceType | String | Yes | Copy trade position type `percent` Set the percentage of the copy trade amount to the trader's elite trade amount. For example, 1 means the follower invests the same amount to open a position as the elite trader, and 2 means the follower invests twice the amount of the elite trader. `amount` the fixed volume specified for copy trading `count` number of copy trade orders with fixed volume (only take effect when parameter mode is advanced) |
| >traceValue | String | Yes | Copy trade position value |
| >maxHoldSize | String | No | Maximum number of orders |
| >stopSurplusRatio | String | No | Take-profit ratio  Positive integers within 1-400, Value exceeding this number is invalid. |
| >stopLossRatio | String | No | Stop-loss ratio   Positive integers within 1-400, Value exceeding this number is invalid. Stop-loss ratio |

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
| data | String | Result `success` `fail` |