# Change Copy Trade Symbol Setting

Rate limit: 5 req/sec/UID

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/copy/mix-trader/config-setting-symbols

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/copy/mix-trader/config-setting-symbols" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*******" \  
  -H "ACCESS-PASSPHRASE:*****" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json" \  
  -d '{"settingList":[{"symbol":"BTCUSDT","productType":"USDT-FUTURES","settingType":"add","stopSurplusRatio":"100","stopLossRatio":"30"}]}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| settingList | List | Yes | Setting overview Maximum: 50 |
| >symbol | String | Yes | Trading pair |
| >productType | String | Yes | Product type `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures |
| >settingType | String | Yes | Setting type, `ADD`, `DELETE`, `UPDATE` |
| >stopSurplusRatio | String | No | Take-profit ratio  positive integers within 1-400,Value exceeding this number is invalid. 2. When a type is deleted: this value is invalid. 3. When a type is added: when the take-profit ratio is empty, then the take-profit ratio is not set by default. 4. When a type is updated: if the value is empty, it means that no change is made; if it is 0, it means that the previously set take-profit is canceled; if it is greater than 0, it means that the take-profit is added or updated. One of stopSurplusRatio and stopLossRatio must be passed when the type is updated. |
| >stopLossRatio | String | No | Stop-loss ratio positive integers within 1-400,Value exceeding this number is invalid. 2. When a type is deleted: this value is invalid. 3. When a type is added: when the stop-loss ratio is empty, then the stop-loss ratio is not set by default. 4. When a type is updated: if the value is empty, it means that no change is made; if it is 0, it means that the previously set take-profit is canceled; if it is greater than 0, it means that the stop-loss is added or updated.` One of stopSurplusRatio and stopLossRatio must be passed when the type is updated. |

Response example

```json
{  
    "code": "00000",  
    "data": "success",  
    "msg": "success",  
    "requestTime": 1627354109502  
}
```

### Response parameters[​](#response-parameters "Direct link to Response parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| data | String | Setting results |