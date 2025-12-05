# Get History Tracking Orders

Rate Limit: 5 req/sec/UID

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/copy/mix-follower/query-history-orders

Request Example

```json
curl "https://api.bitget.com/api/v2/copy/mix-follower/query-history-orders?productType=usdt-futures&symbol=BTCUSDT&endTime=1695721038000&startTime=1692599209000&limit=1" \  
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

Request Example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1695808417159,  
    "data": {  
        "trackingList": [  
            {  
                "trackingNo": "123123123123",  
                "posSide": "long",  
                "openLeverage": "20",  
                "openSize": "0.1852",  
                "closeSize": "0.1852",  
                "openPriceAvg": "32000.5",  
                "closePriceAvg": "28233.0",  
                "achievedPL": "-697.74100000",  
                "openFee": "-5.92649260",  
                "closeFee": "-5.22875160",  
                "symbol": "BTCUSDT",  
                "profitRate": "-235.47",  
                "netProfit": "-697.74100000",  
                "openOrderId": "1",  
                "closeOrderId": "1",  
                "openTime": "1695176941362",  
                "closeTime": "1695353868557",  
                "traderId": "**********",  
                "productType": "usdt-futures"  
            }  
        ],  
        "endId": ""  
    }  
}
```

### Response parameters[​](#response-parameters "Direct link to Response parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| trackingList | List | Overview of elite trade records |
| >trackingNo | String | Order number tracking |
| >traderId | String | Trader user ID |
| >openOrderId | String | Opening order ID |
| >closeOrderId | String | Closing order ID |
| >productType | String | Product type default `USDT-FUTURES` `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures |
| >symbol | String | Trading pair |
| >posSide | String | Position direction `long`: long position in hedging mode `short`: short position in hedging mode |
| >openLeverage | String | Leverage for opening position |
| >openPriceAvg | String | Average entry price |
| >openTime | String | Position opening time (millisecond timestamp) |
| >openSize | String | Opening volume |
| >closePriceAvg | String | Average closing price |
| >closeFee | String | close fee (excluding discounts) |
| >openFee | String | Opening fee (excluding discounts) |
| >closeSize | String | Closing volume |
| >closeTime | String | Closing volume |
| >profitRate | String | rate of return |
| >netProfit | String | follower net income |
| >achievedPL | String | Realized profit and loss |
| endId | String | Last tracking order ID. This is used when idLessThan/idGreaterThan is set as the querying scope |