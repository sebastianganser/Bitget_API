# Get History Tracking Orders

Rate Limit: 5req/sec/UID

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/copy/spot-trader/order-history-track

Request Example

```json
curl "https://api.bitget.com/api/v2/copy/spot-trader/order-history-track?idLessThan=100&idGreaterThan=10&startTime= 1627354109502&endTime=1627354129502&limit=50&symbol=ethusdt" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*******" \  
  -H "ACCESS-PASSPHRASE:*****" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json"```  
  
### Request Parameter  
  
| Parameter Name | Parameter Type | Required |                              Description                              |  
| :---- | :---- | :---- | :---- |  
| idLessThan | String | No | Request the paging content before this ID (older data), and the passed value is the endId of the corresponding interface. |  
| idGreaterThan | String | No | Request the paging content after this ID (updated data). The value passed is the endId of the corresponding interface. |  
| startTime | String | No | start time |  
| endTime | String | No | end time |  
| limit | String | No | Number of queries: Default 20, maximum 100 |  
| symbol | String | No | symbol |  
  
  
  
  
  
</div>  
  
<div class="api-br-10"></div>  
  
  
<div class="api-aligning">  
  
```json title="Response example"  
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1695805248324,  
    "data": {  
        "endId": "1",  
        "trackingList": [  
            {  
                "trackingNo": "1",  
                "fillSize": "0.0317",  
                "buyPrice": "34869.2",  
                "sellPrice": "34865.5",  
                "achievedPL": "-0.78259",  
                "buyTime": "1695728919902",  
                "sellTime": "1695729885589",  
                "buyFee": "-0.00001908",  
                "sellFee": "-0.66314181",  
                "achievedPLR": "-0.07",  
                "symbol": "BTCUSDT",  
                "netProfit": "-1.44573",  
                "followCount": "1"  
            }  
        ]  
    }  
}
```

### Response Description[​](#response-description "Direct link to Response Description")

| Parameter | Parameter Type | Description |
| --- | --- | --- |
| trackingList | List | Overview of elite trade records |
| > trackingNo | String | Track order number |
| > fillSize | String | Filled quantity |
| > buyPrice | String | buy price |
| > sellPrice | String | sell price |
| > achievedPL | String | Realized PnL |
| > buyTime | String | Time of buying |
| > sellTime | String | Time of selling |
| > buyFee | String | Buying transaction fee |
| > sellFee | String | Selling transaction fee |
| > achievedPLR | String | ROI of realized PnL. If the value is 11.11, it represents 11.11%. |
| > symbol | String | Trading pair |
| > netProfit | String | Net profit (negative value presents a loss) |
| > followCount | String | Number of followers for this order |
| endId | String | The last tracking order id.  This shall prevail when specifying idLessThan/idGreaterThan as the range query |