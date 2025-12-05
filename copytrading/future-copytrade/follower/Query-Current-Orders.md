# Get Current Tracking Orders

Rate Limit: 5 req/sec/UID

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/copy/mix-follower/query-current-orders

Request Example

```json
curl "https://api.bitget.com/api/v2/copy/mix-follower/query-current-orders?productType=usdt-futures&symbol=BTCUSDT&endTime=1695721038000&startTime=1692599209000&limit=1" \  
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
| idLessThan | String | No | Separate page content before this ID is requested (older data), and the value input should be the end ID of the corresponding interface. |
| idGreaterThan | String | No | Separate page content after this ID is requested (newer data), and the value input should be the end ID of the corresponding interface. |
| startTime | String | No | Start timestamp  (Copy trade creation time) Milliseconds format of timestamp Unix, e.g. 1597026383085 (The maximum time span supported is three months. The default end time is three months if no value is set for the end time. ) |
| endTime | String | No | End timestamp  (Copy trade creation time) Milliseconds format of timestamp Unix, e.g. 1597026383085 (The maximum time span supported is three months. The default start time is three months ago if no value is set for the start time. ) |
| limit | String | No | Number of queries: Default: 20, maximum: 100. |
| symbol | String | No | Trading pairs, case sensitive |
| productType | String | Yes | Product type `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures |
| traderId | String | No | Trader ID |

Response example

```json
{  
    "code": "00000",  
    "data": [  
        {  
            "trackingNo": "1",  
            "traderName": "xxxxxx",  
            "openOrderId": "1",  
            "closeOrderId": "",  
            "traderId": "**********",  
            "symbol": "BTCUSDT",  
            "posSide": "short",  
            "openLeverage": "47",  
            "openAvgPrice": "39827",  
            "openTime": "1627567376984",  
            "openSize": "0.0010000000000000",  
            "closeAvgPrice": "0",  
            "closeSize": "0.0000000000000000",  
            "openMarginSz": "21",  
            "closeTime": "0"  
        }  
    ],  
    "msg": "success",  
    "requestTime": 1634107646972  
}
```

### Response parameters[​](#response-parameters "Direct link to Response parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| trackingNo | String | Track order number |
| traderId | String | Trader user ID |
| traderName | String | Trader alias |
| openOrderId | String | Opening order ID |
| closeOrderId | String | Closing order ID |
| symbol | String | Trading pair |
| posSide | String | Position direction `long`: long position in hedging mode `short`: short position in hedging mode |
| openLeverage | String | Leverage for opening position |
| openPriceAvg | String | Average entry price |
| openTime | String | Position opening time (millisecond timestamp) |
| openFee | String | Opening fee (excluding discounts) |
| openSize | String | Opening volume |
| openMarginSz | String | Margin amount |
| closeAvgPrice | String | Average closing price |
| closeSize | String | Closing volume |
| closeTime | String | Position closing time (millisecond timestamp) |