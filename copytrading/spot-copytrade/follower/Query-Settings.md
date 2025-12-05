# Get Follow Configuration

Rate Limit: 10 req/sec/UID

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/copy/spot-follower/query-settings

Request Example

```json
curl "https://api.bitget.com/api/v2/copy/spot-follower/query-settings?traderId=bfxxxxxx" \  
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
| traderId | String | Yes | Trader user ID |

Response example

```json
{  
        "code": "00000",  
        "data": {  
                "enable": "YES",  
                "profitRate": "5",  
                "settledInDays": "53",  
                "tradeSettingList": [{  
                        "maxTraceAmount": "50000",  
                        "stopLossRation": "10",  
                        "stopSurplusRation": "10",  
                        "symbol": "ETHUSDT",  
                        "traceType": "FIXED_AMOUNT"  
                }],  
                "tradeSymbolSettingList": [{  
                        "maxStopLossRation": "90",  
                        "maxStopSurplusRation": "500",  
                        "maxTraceAmount": "1200",  
                        "maxTraceAmountSystem": "50000",  
                        "maxTraceSize": "500",  
                        "maxTraceRation": "20",  
                        "minStopLossRation": "0",  
                        "minStopSurplusRation": "0",  
                        "minTraceAmount": "10",  
                        "minTraceSize": "0.001",  
                        "minTraceRation": "0.1",  
                        "sliderMaxStopLossRatio": "90",  
                        "sliderMaxStopSurplusRatio": "500",  
                        "symbol": "BTCUSDT"  
                }],  
                "traderHeadPic": "",  
                "traderName": "139****0981"  
        },  
        "msg": "success",  
        "requestTime": 1682401856339  
}
```

### Response Description[​](#response-description "Direct link to Response Description")

| Parameter | Parameter Type | Description |
| --- | --- | --- |
| enable | String | Am I following |
| profitRate | String | profit Rate |
| settledInDays | String | Trader membership period (starting from the registration date) |
| traderHeadPic | String | trader avatar |
| traderName | String | trader nick name |
| tradeSettingList | list | My copy trade settings |
| > maxTraceAmount | String | Maximum copy trade buying coin (base currency) |
| > stopLossRation | String | Stop-loss ratio  If the value is 11.11, it represents 11.11% |
| > stopSurplusRation | String | Take-profit ratio  If the value is 11.11, it represents 11.11% |
| > symbol | String | Trading pair ID |
| > traceType | String | Copy trade type `percent` Set the percentage of the copy trade amount to the trader's elite trade amount. For example, 1 means the follower invests the same amount to open a position as the elite trader, and 2 means the follower invests twice the amount of the elite trader. `amount` The fixed volume specified for copy trading `count` Number of copy trade orders with fixed volume |
| tradeSymbolSettingList | List | Trading pair copy trading configuration |
| > maxStopLossRation | String | Maximum stop-loss ratio If the value is 11.11, it represents 11.11% |
| > maxStopSurplusRation | String | Maximum take-profit ratio If the value is 11.11, it represents 11.11% |
| > maxTraceAmount | String | Maximum copy trading volume (single order) |
| > maxTraceAmountSystem | String | System configuration for the maximum buying amount |
| > maxTraceSize | String | Maximum amount for copy trading |
| > maxTraceRation | String | Maximum copy trade ratio   (2 decimal places, e.g. 0.11 for 11%) If the value is 11.11, it represents 11.11% |
| > minStopLossRation | String | Minimum stop-loss ratio   (2 decimal places, e.g. 0.11 for 11%) If the value is 11.11, it represents 11.11% |
| > minStopSurplusRation | String | Minimum take-profit ratio  If the value is 11.11, it represents 11.11% |
| > minTraceAmount | String | Minimum copy trading volume |
| > minTraceSize | String | Minimum copy trade volume |
| > minTraceRation | String | Minimum order ratio |
| > sliderMaxStopLossRatio | String | Maximum stop loss ratio of slider |
| > sliderMaxStopSurplusRatio | String | Maximum take-profit ratio of slider |
| > symbol | String | Trading pair |
| endId | String | The last data id. The id value is the tracking number, used to query based on id |