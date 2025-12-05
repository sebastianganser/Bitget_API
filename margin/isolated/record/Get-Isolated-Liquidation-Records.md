# Get Isolated Liquidation History

Frequency limit: 10 times/1s (UID)

### Description[​](#description "Direct link to Description")

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/margin/isolated/liquidation-history

Request Example

```json
curl "https://api.bitget.com/api/v2/margin/isolated/liquidation-history?symbol=BTCUSDT&startTime=1692690126000"  -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*******" \  
   -H "ACCESS-PASSPHRASE:*****" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| symbol | String | Yes | Trading pair |
| startTime | String | Yes | Start time, Unix millisecond timestamps |
| endTime | String | No | End time, Unix millisecond timestamps Maximum interval between start and end times is 90 days |
| limit | String | No | Number of queries Default: 100, maximum: 500 |
| idLessThan | String | No | For turning pages. No setting is needed when querying for the first time. Set to to smallest liqId returned from the last query when searching for data in the second page and other paged. Data smaller than the liqId entered will be returned. This is designed to shorten the query response time. |

Response Example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1695624945382,  
  "data": {  
    "resultList": [  
      {  
        "liqId": "123",  
        "symbol": "BTCUSDT",  
        "liqStartTime": "1653453245342",  
        "liqEndTime": "16312423423432",  
        "liqRiskRatio": "1.01",  
        "totalAssets": "1242.34",  
        "totalDebt": "1100",  
        "liqFee": "1.2",  
        "cTime": "1653453245342",  
        "uTime": "1692690126000"  
      }  
    ],  
    "maxId": "1",  
    "minId": "1"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| resultList | List | List |
| > symbol | String | Trading pair |
| > liqId | String | Liquidation ID |
| > liqStartTime | String | Start time of liquidation |
| > liqEndTime | String | Liquidation end time |
| > liqRiskRatio | String | Risk ratio at liquidation |
| > totalAssets | String | Total assets at liquidation in USDT |
| > totalDebt | String | Total borrowings at liquidation in USDT |
| > liqFee | String | Liquidation fees |
| > cTime | String | Creation time, millisecond timestamp |
| > uTime | String | Update time, millisecond timestamp |
| maxId | String | Max ID of current search result |
| minId | String | Min ID of current search result, use: `idLessThan=minId` in the next query |