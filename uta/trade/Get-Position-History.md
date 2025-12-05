# Get Positions History

### Description[​](#description "Direct link to Description")

Query historical positions within the last 90 days.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/position/history-position
* Rate limit: 20/sec/UID
* Permission: UTA trade (read & write)

Request

```json
curl "https://api.bitget.com/api/v3/position/history-position?productType=USDT-FUTURES" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| category | String | Yes | Product type  `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures |
| symbol | String | No | Symbol name e.g.,`BTCUSDT` |
| startTime | String | No | Start timestamp  A Unix timestamp in milliseconds e.g.,`1597026383085` The access window is 90 days |
| endTime | String | No | End timestamp  A Unix timestamp in milliseconds e.g.,`1597026383185`  The time range between `startTime` and `endTime` must not exceed 30 days |
| limit | String | No | Limit per page Default:`100`. Maximum:`100` |
| cursor | String | No | Cursor  Pagination is implemented by omitting the cursor in the first query and applying the cursor from the previous query for subsequent pages |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1730186957802,  
  "data": {  
    "list": [  
      {  
        "positionId": "1111111111111111111",  
        "category": "USDT-FUTURES",  
        "symbol": "EOSUSDT",  
        "marginCoin": "USDT",  
        "holdMode": "one_way_mode",  
        "posSide": "long",  
        "marginMode": "crossed",  
        "openPriceAvg": "1960.001",  
        "closePriceAvg": "1959.999",  
        "openTotalPos": "58",  
        "closeTotalPos": "58",  
        "cumRealisedPnl": "-0.116",  
        "netProfit": "-45.588",  
        "totalFunding": "0",  
        "openFeeTotal": "-22.7360116",  
        "closeFeeTotal": "-22.7359884",  
        "createdTime": "1729928018076",  
        "updatedTime": "1729929656321"  
      }  
    ],  
    "cursor": "1111111111111111111"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| list | Array | List |
| >positionId | String | Position ID |
| >category | String | Product Type   `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures |
| >symbol | String | Symbol name |
| >marginCoin | String | Margin coin |
| >posSide | String | Position side `long`/`short` |
| >openPriceAvg | String | Average opening price |
| >closePriceAvg | String | Average closing price |
| >openTotalPos | String | Total open position |
| >closeTotalPos | String | Total closed position |
| >marginMode | String | Margin mode `crossed`/`isolated` |
| >holdMode | String | Holding mode `one_way_mode` /`hedge_mode` |
| >cumRealisedPnl | String | Cumulative realised profit and loss Excluding fees and funding costs |
| >netProfit | String | Net profit and loss Including fees and funding costs |
| >totalFunding | String | Total funding The accumulated fund fee during the position's duration. If the value is zero, it indicates no fees have been charged |
| >openFeeTotal | String | Fees deducted on position opening  Opening fees deducted during the position's lifetime |
| >closeFeeTotal | String | Fees deducted on position closing  Closing fees deducted during the position's lifetime |
| >createdTime | String | Position created timestamp   A Unix millisecond timestamp |
| >updatedTime | String | Position updated timestamp   A Unix millisecond timestamp |
| cursor | String | Cursor |