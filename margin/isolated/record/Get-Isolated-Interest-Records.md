# Get Isolated Interest History

Frequency limit: 10 times/1s (UID)

### Description[​](#description "Direct link to Description")

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/margin/isolated/interest-history

Request Example

```json
curl "https://api.bitget.com/api/v2/margin/isolated/interest-history?coin=USDT&startTime=1695336324000&symbol=BTCUSDT"  -H "ACCESS-KEY:*******" \  
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
| coin | String | No | Coin |
| startTime | String | Yes | Start time, Unix millisecond timestamps |
| endTime | String | No | End time, Unix millisecond timestamps Maximum interval between start and end times is 90 days |
| limit | String | No | Number of queries Default: 100, maximum: 500 |
| idLessThan | String | No | For turning pages. No setting is needed when querying for the first time. Set to to smallest interestId returned from the last query when searching for data in the second page and other paged. Data smaller than the interestId entered will be returned. This is designed to shorten the query response time. |

Response Example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1695624945382,  
  "data": {  
    "resultList": [  
      {  
        "interestId": "1",  
        "interestCoin": "USDT",  
        "dailyInterestRate": "0.24",  
        "loanCoin": "USDT",  
        "interestAmount": "0.01",  
        "interstType": "first",  
        "symbol": "BTCUSDT",  
        "cTime": "1695624061276",  
        "uTime": "1695624061276"  
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
| > interestId | String | Interest ID |
| > interestAmount | String | Amount of interest |
| > dailyInterestRate | String | Daily interest rate |
| > interstType | String | Type of interest first: Interest on initial borrowing scheduled: scheduled interest |
| > interestCoin | String | Interest coin |
| > loanCoin | String | Borrowing coin |
| > cTime | String | Creation time, millisecond timestamp |
| > uTime | String | Update time, millisecond timestamp |
| maxId | String | Max ID of current search result |
| minId | String | Min ID of current search result, use: `idLessThan=minId` in the next query |