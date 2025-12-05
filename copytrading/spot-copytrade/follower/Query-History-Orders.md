# Get History Tracking Orders

Rate Limit: 5 req/sec/UID

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/copy/spot-follower/query-history-orders

Request Example

```json
curl "https://api.bitget.com/api/v2/copy/spot-follower/query-history-orders" \  
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
| traderId | String | No | trader Id |
| idLessThan | String | No | Before requesting this ID |
| idGreaterThan | String | No | After requesting this ID |
| startTime | String | No | start time |
| endTime | String | No | end time |
| limit | String | No | The default is 20, with a maximum support of 50. More than 20 items will be returned |

Response example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1695811537460,  
    "data": {  
        "endId": "1",  
        "trackingList": [  
            {  
                "trackingNo": "1",  
                "traderId": "**********",  
                "fillSize": "0.0316",  
                "buyPrice": "34870.7",  
                "sellPrice": "34865.5",  
                "buyFee": "-0.00001902",  
                "sellFee": "-0.66104988",  
                "achievedPL": "-0.82756",  
                "achievedPLR": "-0.07",  
                "symbol": "BTCUSDT",  
                "buyTime": "1695729617968",  
                "sellTime": "1695729886269"  
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
| > fillSize | String | Filled quantity |
| > buyPrice | String | Average buying price |
| > sellPrice | String | Average selling price |
| > achievedPL | String | Realized PnL |
| > buyTime | String | Time of buying |
| > sellTime | String | Time of selling |
| > buyFee | String | Buying transaction Fee |
| > sellFee | String | Selling transaction fee |
| > achievedPLR | String | ROI of realized PnL. If the value is 11.11, it represents 11.11%. |
| > symbol | String | Trading pair |
| endId | String | The final data ID. The ID value is the tracking number used for querying based on the ID |