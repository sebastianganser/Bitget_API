# Get Copy Trade Settings

Rate Limit: 5 req/sec/UID

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/copy/mix-follower/query-settings

Request Example

```json
curl "https://api.bitget.com/api/v2/copy/mix-follower/query-settings?traderId=123123123" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*******" \  
  -H "ACCESS-PASSPHRASE:*****" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| traderId | String | Yes | ID of the elite trader that you followed |

Response example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1679465100798,  
    "data": {  
        "followerEnable": "YES",  
        "detailList": [  
            {  
                "symbol": "ETHUSDT",  
                "productType": "USDT-FUTURES",  
                "marginType": "specify",  
                "marginCoin": "USDT",  
                "leverType": "trader",  
                "longLeverage": "20",  
                "shortLeverage": "20",  
                "traceType": "percent",  
                "traceValue": "1",  
                "maxHoldSize": "50000",  
                "stopSurplusRatio": "200",  
                "stopLossRatio": ""  
            }  
        ]  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| followerEnable | String | Am I following YES NO |
| detailList | List | Copy trade details |
| > symbol | String | Trading pair |
| > productType | String | Product type `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures |
| > marginType | String | Margin type `trader` margin type of the elite trader that you followed; `specify` your own margin type. |
| > marginCoin | String | Margin currency |
| > leverType | String | Leverage type `position` use position leverage; `specify` use the specified leverage; `trader` use the leverage of the elite trader; |
| > longLeverage | String | Leverage of long positions |
| > shortLeverage | String | Leverage of short positions |
| > traceType | String | Copy trade position type `percent` Set the percentage of the copy trade amount to the trader's elite trade amount. For example, 1 means the follower invests the same amount to open a position as the elite trader, and 2 means the follower invests twice the amount of the elite trader. `amount` the fixed volume specified for copy trading `count` number of copy trade orders with fixed volume |
| > traceValue | String | Copy trade position value |
| > maxHoldSize | String | Maximum number of orders |
| > stopSurplusRatio | String | Take-profit ratio positive integers within 1-400, Value exceeding this number is invalid. |
| > stopLossRatio | String | Stop-loss ratio positive integers within 1-400, Value exceeding this number is invalid. |