# Get History Tracking Orders

Rate Limit: 5 req/sec/UID

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/copy/mix-trader/order-history-track

Request Example

```json
curl "https://api.bitget.com/api/v2/copy/mix-trader/order-history-track?productType=USDT-FUTURES&symbol=BTCUSDT&startTime=1692674087000&endTime=1695035411000&order=desc&limit=20" \  
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
| idLessThan | String | No | Separate page content before this ID is requested (older data), and the value input should be the endid of the corresponding interface. |
| idGreaterThan | String | No | Separate page content after this ID is requested (newer data), and the value input should be the endid of the corresponding interface. |
| startTime | String | No | Start timestamp  (order creation time) Milliseconds format of timestamp Unix, e.g. 1597026383085 (The maximum time span supported is three months. The default end time is three months if no value is set for the end time. ) |
| endTime | String | No | End timestamp  (order creation time) Milliseconds format of timestamp Unix, e.g. 1597026383085 (The maximum time span supported is three months. The default start time is three months ago if no value is set for the start time. ) |
| limit | String | No | Number of queries: Default: 20, maximum: 100. |
| order | String | No | Sorting rules (creation time): Default: desc |
| symbol | String | No | Trading pair Supports capital and lower-case letters |
| productType | String | Yes | Product type `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures |

Response example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1695802740184,  
    "data": {  
        "trackingList": [  
            {  
                "trackingNo": "123123",  
                "symbol": "BTCUSDT",  
                "openOrderId": "12312313123",  
                "closeOrderId": "12312313123",  
                "productType": "usdt-futures",  
                "posSide": "long",  
                "openLeverage": "20",  
                "openPriceAvg": "32000.5",  
                "openTime": "1695035398292",  
                "openSize": "0.1000",  
                "closeSize": "0.1000",  
                "closeTime": "1695176679764",  
                "closePriceAvg": "32000.0",  
                "stopType": "",  
                "achievedPL": "-0.05000000",  
                "openFee": "-3.20005000",  
                "closeFee": "-3.20000000",  
                "cTime": "1695035398292"  
            }  
        ],  
        "endId": "1"  
    }  
}
```

### Response parameters[​](#response-parameters "Direct link to Response parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| trackingList | List | Overview of elite trade records |
| >trackingNo | String | Track order number |
| >symbol | String | Trading pair name |
| >productType | String | Product type `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures |
| >openOrderId | String | Opening order ID |
| >closeOrderId | String | Closing order ID |
| >posSide | String | Position direction `long`: long position in hedging mode `short`: short position in hedging mode |
| >openLeverage | String | Leverage to open positions |
| >openAvgPrice | String | Average entry price |
| >openTime | String | Time to open position (milliseconds) |
| >closeTime | String | Time to close position (milliseconds) |
| >closeAvgPrice | String | Average exit price |
| >stopType | String | Type of position closed `profit` `loss` |
| >achievedPL | String | Realized PnL |
| >openFee | String | Opening fee (Shows USDT only, not coupons) |
| >closeFee | String | Closing fee (Shows USDT only, not coupons) |
| >openSize | String | Position size to open |
| >closeSize | String | Closed quantity |
| >cTime | String | Order creation time |
| endId | String | Final tracking order ID. This is used when idLessThan/idGreaterThan is set as a range. |