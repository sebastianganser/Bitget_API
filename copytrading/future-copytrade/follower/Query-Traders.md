# Get My Traders

Rate Limit: 5 req/sec/UID

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/copy/mix-follower/query-traders

Request Example

```json
curl "https://api.bitget.com/api/v2/copy/mix-follower/query-traders?startTime=1693205171000&endTime=1694498173000&pageSize=20&pageNo=1" \  
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
| startTime | String | No | Start timestamp  Milliseconds format of timestamp Unix, e.g. 1597026383085 (The maximum time span supported is three months. The default end time is three months if no value is set for the end time. ) |
| endTime | String | No | End timestamp  Milliseconds format of timestamp Unix, e.g. 1597026383085 (The maximum time span supported is three months. The default start time is three months ago if no value is set for the start time. ) |
| pageNo | String | No | Current page number Default to 1. |
| pageSize | String | No | Number of quiries Default to 20 entries and supports a maximum of 50 entries. |

Response example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1695812788826,  
    "data": [  
        {  
            "certificationType": "Uncertified",  
            "traderId": "**********",  
            "traderName": "x-1111111",  
            "maxFollowLimit": "1000",  
            "followCount": "0",  
            "traceTotalMarginAmount": "1185.3286",  
            "traceTotalNetProfit": "-744.7362",  
            "traceTotalProfit": "-698.0210",  
            "currentTradingPairs": [  
                "BTCUSDT",  
                "BTCUSD",  
                "EOSUSDT",  
                "ETHUSDT",  
                "ETHUSD"  
            ],  
            "followerTime": "1693381832000",  
            "bgbMaxFollowLimit": "100",  
            "bgbFollowCount": "0"  
        }  
    ]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| certificationType | String | Certification type `Uncertified` `Certified` |
| traderId | String | Trader ID |
| traderName | String | Alias |
| maxFollowLimit | String | Maximum number of elite traders to follow |
| bgbMaxFollowLimit | String | Maximum number of elite traders to follow granted by BGB holdings |
| followCount | String | Number of elite traders that you have followed |
| bgbFollowCount | String | Number of elite traders that you have followed granted by BGB holdings |
| traceTotalMarginAmount | String | Total opening margin |
| traceTotalNetProfit | String | Total net profit |
| traceTotalProfit | String | Total profit |
| currentTradingPairs | List<String> | Current underlying assets for copy trading |
| followerTime | String | Following date (take the first following date) Milliseconds format of timestamp Unix, e.g. 1597026383085 |