# Get Current Copy Trade Orders

Rate limit: 5 req/sec/UID

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/copy/spot-follower/query-current-orders

Request Example

```json
curl "https://api.bitget.com/api/v2/copy/spot-follower/query-current-orders" \  
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
| traderId | String | No | trader id |
| idLessThan | String | No | Before requesting this ID |
| idGreaterThan | String | No | After requesting this ID |
| startTime | String | No | start time |
| endTime | String | No | end time ） |
| limit | String | No | The default is 20, with a maximum support of 50. More than 20 items will be returned |

Response example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1695809370190,  
    "data": {  
        "endId": "1",  
        "trackingList": [  
            {  
                "trackingNo": "1",  
                "traderId": "**********",  
                "buyFillSize": "0.0317",  
                "buyDelegateSize": "0.0317190800000000",  
                "buyPrice": "34870.7",  
                "unrealizedPL": "-0.77945295",  
                "buyTime": "1695729895491",  
                "buyFee": "-0.00001908",  
                "unrealizedPLR": "-0.07",  
                "symbol": "BTCUSDT",  
                "stopSurplusPrice": null,  
                "stopLossPrice": null  
            }  
        ]  
    }  
}
```

### Response Description[​](#response-description "Direct link to Response Description")

| Parameter | Parameter Type | Description |
| --- | --- | --- |
| trackingList | list | tracking list |
| > trackingNo | String | Track order number |
| > traderId | String | trader Id |
| > buyFillSize | String | Filled buy quantity |
| > buyDelegateSize | String | Buy order quantity |
| > buyPrice | String | buy price |
| > unrealizedPL | String | Current unrealized PnL |
| > buyTime | String | Time of buying |
| > buyFee | String | Buying transaction Fee |
| > unrealizedPLR | String | Current ROI of unrealized PnL  If the value is 11.11, it represents 11.11% |
| > symbol | String | Trading pair |
| > stopSurplusPrice | String | Stop profit price |
| > stopLossPrice | String | Stop loss price |
| endId | String | The final data ID. The ID value is the tracking number used for querying based on the ID |