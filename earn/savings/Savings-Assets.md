# Savings Assets

Frequency limit: 10c/1s (Uid)

### Description[​](#description "Direct link to Description")

Get savings assets

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/earn/savings/assets

Request Example

```json
curl "https://api.bitget.com/api/v2/earn/savings/assets?periodType=fixed&pageSize=20" \  
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
| periodType | String | Yes | Period type flexible demand deposit  fixed time deposit |
| startTime | String | No | Start timestamp  (Savings creation time) Milliseconds format of timestamp Unix, e.g. 1597026383085 (The maximum time span supported is three months. The default start time is three months ago if no value is set for the start time. ) |
| endTime | String | No | End timestamp  (Savings creation time) Milliseconds format of timestamp Unix, e.g. 1597026383085 (The maximum time span supported is three months. The default end time is now if no value is set for the end time. ) |
| limit | String | No | Number of queries: Default: 20, maximum: 100. |
| idLessThan | String | No | Separate page content before this ID is requested (older data), and the value input should be the end ID of the last request. |

Response Example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1696748867881,  
    "data": {  
        "resultList": [  
            {  
                "productId": "123123123",  
                "orderId": "xxxx",  
                "productCoin": "BGB",  
                "interestCoin": "BGB",  
                "periodType": "flexible",  
                "period": "",  
                "holdAmount": "100.000",  
                "lastProfit": "0.01643800",  
                "totalProfit": "1.25479000",  
                "holdDays": "",  
                "status": "in_holding",  
                "allowRedemption": "",  
                "productLevel": "normal",  
                "apy": [  
                    {  
                        "rateLevel": "1",  
                        "minApy": "0.000000",  
                        "maxApy": "200.000000",  
                        "currentApy": "6.00"  
                    }  
                ]  
            }  
        ],  
        "endId": "123456789"  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| resultList | List<Object> | Savings assets list |
| > productId | String | Product ID |
| > orderId | String | assets order ID   only for `fixed` |
| > productCoin | String | Savings subscription coin |
| > interestCoin | String | Interest earning coin |
| >periodType | String | Period type  `flexible` flexible current  `fixed` fixed term |
| >period | String | Duration `flexible` This value is not returned |
| >holdAmount | String | Current subscription size |
| >lastProfit | String | Profit in the last day |
| >totalProfit | String | Profit in total |
| >holdDays | String | Days of holding |
| >status | String | Product Status `in_progress` Subscription in progress  `in_redemption` Redemption in progress |
| >advanceRedeem | String | Whether early redemption is allowed  `Yes` allowed  `No` not allowed |
| apy | List<Object> | Ladder interest rate info |
| > rateLevel | String | Rate level |
| > minApy | String | Minimum APY |
| > maxApy | String | Maximum APY |
| > currentApy | String | Current tiered APY |