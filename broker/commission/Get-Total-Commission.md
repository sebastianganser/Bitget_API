# Get Total Commission

Rate limit: 20/sec/UID

### Description[​](#description "Direct link to Description")

* Data retention: 365 days
* Historical data available from: 2025/6/1
* Data granularity: daily
* Data update granularity: daily, previous day’s data is updated on the current day
* Time zone: UTC+8
* startTime and endTime should either both be set or both left unset
* This API supports retrieving data within the past 365 days (data is available starting from 2025/6/1 at the earliest)
* If startTime and endTime are not set in the request, the default returned information will be for yesterday (00:00-23:
  59 UTC+8)
* Data update frequency: T+1 (UTC+8)

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/broker/total-commission

Request

```json
curl "https://api.bitget.com/api/v2/broker/total-commission" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*" \  
  -H "ACCESS-PASSPHRASE:*" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| startTime | String | No | Start timestamp in milliseconds. If both startTime and endTime are empty, the default time range is yesterday 00:00–23:59 (UTC+8). startTime and endTime must either both be set or both left unset. An error will be returned if the range exceeds 180 days. |
| endTime | String | No | End timestamp in milliseconds. If both startTime and endTime are empty, the default time range is yesterday 00:00–23:59 (UTC+8). startTime and endTime must either both be set or both left unset. An error will be returned if the range exceeds 180 days. |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 17609760000000,  
  "data": [  
    {  
      "date": "17609760000000",  
      "totalTradingVolume": "24679.848225",  
      "totalActiveTraders": "1",  
      "totalCommission": "0",  
      "spot": {  
        "spotTradingVolume": "419.847925",  
        "spotTradingFee": "0.34999881",  
        "spotPureTradingFee": "0.34999881",  
        "spotCommission": "0"  
      },  
      "futures": {  
        "futuresTradingVolume": "24260.0003",  
        "futuresTradingFee": "15.5999965399983",  
        "futuresPureTradingFee": "15.5999965399983",  
        "futuresCommission": "0"  
      }  
    }  
  ]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| date | String | Commission date |
| totalTradingVolume | String | Broker’s total trading volume for the day |
| totalActiveTraders | String | Number of active traders for the broker that day |
| totalCommission | String | Total commission earned by the broker (USDT) |
| spot | object | Spot data |
| > spotTradingVolume | String | Spot trading volume (USDT) |
| > spotTradingFee | String | Actual spot trading fee collected (USDT) |
| > spotPureTradingFee | String | Net spot trading fee (USDT) (after deducting negative maker, etc.; used as the base for commission calculation) |
| > spotCommission | String | Spot commission (USDT) |
| futures | object | Futures data |
| > futuresTradingVolume | String | Futures trading volume (USDT) |
| > futuresTradingFee | String | Actual futures trading fee collected (USDT) |
| > futuresPureTradingFee | String | Net futures trading fee (USDT) (after deducting negative maker, etc.; used as the base for commission calculation） |
| > futuresCommission | String | Futures commission (USDT) |