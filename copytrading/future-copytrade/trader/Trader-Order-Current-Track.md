# Get Current Tracking Orders

Rate Limit: 5 req/sec/UID

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/copy/mix-trader/order-current-track

Request Example

```json
curl "https://api.bitget.com/api/v2/copy/mix-trader/order-current-track?symbol=BTCUSDT&productType=usdt-futures&limit=20" \  
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
| symbol | String | No | Trading pair Supports capital and lower-case letters |
| productType | String | Yes | Product type `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures |
| startTime | String | No | Start time (greater than or equal to) Unix timestamp in milliseconds format, e.g. 1597026383085, rounded down according to granularity, i.e. for granularity=1m: 1672410799436 (December 30, 2022, 22:33:19) rounded down to 1672410780000 (December 30, 2022, 22:33:00) Request data generated after this start time (If end time is not input, then estimates out the start time based on the current time) |
| endTime | String | No | Start time (greater than or equal to) Unix timestamp in milliseconds format, e.g. 1597026383085, rounded down according to granularity, i.e. for granularity=1m: 1672410799436 (December 30, 2022, 22:33:19) rounded down to 1672410780000 (December 30, 2022, 22:33:00) Request data generated before this start time |
| limit | String | No | default 20, max 50 |
| idGreaterThan | String | No | Requests the content on the page after this ID (newer data), the value input should be the endId of the corresponding interface. |
| idLessThan | String | No | Separate page content before this ID is requested (older data), the value input should be the endId of the corresponding interface. |

Response example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1695801601016,  
    "data": {  
        "trackingList": [  
            {  
                "trackingNo": "1231231231",  
                "openOrderId": "123123123123",  
                "symbol": "BTCUSDT",  
                "posSide": "long",  
                "openLeverage": "20",  
                "openPriceAvg": "26248.9",  
                "openTime": "1695801595658",  
                "openSize": "0.1000000000000000",  
                "presetStopSurplusPrice": "27561.34",  
                "presetStopLossPrice": "25855.16",  
                "openFee": "-2.62489",  
                "followCount": "1"  
            }  
        ],  
        "endId": "1"  
    }  
}
```

### Response parameters[​](#response-parameters "Direct link to Response parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| trackingList | List | Track order list |
| > trackingNo | String | Track order number |
| > symbol | String | Trading pair name |
| > posSide | String | Position direction `long`: long position in hedging mode `short`: short position in hedging mode |
| > openOrderId | String | Elite trader opening order ID |
| > openLeverage | String | Leverage to open positions |
| > openPriceAvg | String | Average entry price |
| > openTime | String | Opening time |
| > openSize | String | Position size to open |
| > presetStopSurplusPrice | String | Set TP price |
| > presetStopLossPrice | String | Set SL price |
| > openFee | String | Opening fee (Shows USDT only, not coupons) |
| > followCount | String | Number of followers for this order |
| endId | String | This is used when idLessThan/idGreaterThan is set as a range. |