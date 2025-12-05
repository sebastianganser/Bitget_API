# Get Current Tracking Orders

Limit rule 10 times/1s (uid)

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/copy/spot-trader/order-current-track

Request Example

```json
curl "https://api.bitget.com/api/v2/copy/spot-trader/order-current-track" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*******" \  
  -H "ACCESS-PASSPHRASE:*****" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json"
```

### Request Parameter[​](#request-parameter "Direct link to Request Parameter")

| Parameter Name | Parameter Type | Required | Description |
| --- | --- | --- | --- |
| symbol | String | No | Trading pair |
| idLessThan | String | No | Before requesting this ID |
| idGreaterThan | String | No | After requesting this ID |
| startTime | String | No | start time |
| endTime | String | No | end time |
| limit | String | No | The default is 20, and the maximum supported is 50. More than 20 items will be returned |

Response example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1695803899870,  
    "data": {  
        "endId": "1",  
        "trackingList": [  
            {  
                "trackingNo": "1",  
                "orderId": "1",  
                "buyFillSize": "0.0317",  
                "buyDelegateSize": "0.0317190800000000",  
                "buyPrice": "34870.7",  
                "unrealizedPL": "-0.79530295",  
                "buyTime": "1695729894873",  
                "buyFee": "-0.00001908",  
                "unrealizedPLR": "-0.07",  
                "symbol": "BTCUSDT",  
                "stopLossPrice": null,  
                "stopSurplusPrice": null,  
                "followCount": "1"  
            }  
        ]  
    }  
}
```

### Response Description[​](#response-description "Direct link to Response Description")

| Parameter | Parameter Type | Description |
| --- | --- | --- |
| trackingList | String | tracking order collection |
| >trackingNo | String | Track order number |
| >orderId | String | order number |
| >buyFillSize | String | Number of filled buy orders |
| >buyDelegateSize | String | Buy order quantity |
| >buyPrice | String | buy Price |
| >unrealizedPL | String | Current unrealized PnL |
| >buyTime | String | Time of buying |
| >buyFee | String | Buying transaction fee |
| >unrealizedPLR | String | ROI of unrealized PnL. If the value is 11.11, it represents 11.11%. |
| >symbol | String | Trading pair |
| >stopLossPrice | String | Stop loss price |
| >stopSurplusPrice | String | Take profit price |
| >followCount | String | Number of followers for this order |
| endId | String | The last data id. The id value is the tracking number, which is used to query based on id. |