# SharkFin Assets

Frequency limit: 10c/1s (Uid)

### Description[​](#description "Direct link to Description")

Get sharkfin assets

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/earn/sharkfin/assets

Request Example

```json
curl "https://api.bitget.com/api/v2/earn/sharkfin/assets?limit=20&status=subscribed" \  
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
| status | String | Yes | Shark status   `subscribed` Subscribed(default)   `settled` Settled |
| startTime | String | No | Start timestamp  (Sharkfin creation time) Milliseconds format of timestamp Unix, e.g. 1597026383085 (The maximum time span supported is three months. The default start time is three months ago if no value is set for the start time. ) |
| endTime | String | No | End timestamp  (Sharkfin creation time) Milliseconds format of timestamp Unix, e.g. 1597026383085 (The maximum time span supported is three months. The default end time is now if no value is set for the end time. ) |
| limit | String | No | Number of queries: Default: 20, maximum: 100. |
| idLessThan | String | No | Separate page content before this ID is requested (older data), and the value input should be the end ID of the last request. |

Response Example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1696756316611,  
    "data": {  
        "resultList": [  
            {  
                "productId": "12312313",  
                "interestStartTime": "1697199180000",  
                "interestEndTime": "1697803980000",  
                "productCoin": "BTC",  
                "subscribeCoin": "USDT",  
                "trend": "up",  
                "settleTime": "1697803980000",  
                "interestAmount": "",  
                "productStatus": "running"  
            }  
        ],  
        "endId": "456456456"  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| resultList | List<Object> | Sharkfin product list info |
| >productId | String | Product ID |
| >interestStartTime | String | Interest accrual start time |
| >interestEndTime | String | Interest accrual end time |
| >productCoin | String | Product subscription coin |
| >subscribeCoin | String | Subscription coin |
| >trend | String | Trend `up` rise `down` fall |
| >settleTime | String | Settlement time, Unix millisecond timestamp |
| >interestAmount | String | Interest amount |
| >productStatus | String | Product status `running` Subscription `pause` pause has been suspended `wait_interest` is pending `wait_settle` is pending settlement `settle` has been settled `redeem` has been redeemed  `sell_out` sold out |