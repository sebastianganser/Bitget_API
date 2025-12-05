# Get Isolated Borrow History

Frequency limit: 10 times/1s (UID)

### Description[​](#description "Direct link to Description")

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/margin/isolated/borrow-history

Request Example

```json
curl "https://api.bitget.com/api/v2/margin/isolated/borrow-history?symbol=BTCUSDT&startTime=1695336324000"  -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*******" \  
   -H "ACCESS-PASSPHRASE:*****" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| symbol | String | Yes | Trading pairs, BTCUSDT |
| loanId | String | No | Borrowing ID (accurate matching of single entry) |
| coin | String | No | Coin |
| startTime | String | Yes | Start time, Unix millisecond timestamps |
| endTime | String | No | End time, Unix millisecond timestamps Maximum interval between start and end times is 90 days |
| limit | String | No | Number of queries Default: 100, maximum: 500 |
| idLessThan | String | No | For turning pages. No setting is needed when querying for the first time. Set to to smallest loanId returned from the last query when searching for data in the second page and other paged. Data smaller than the loanId entered will be returned. This is designed to shorten the query response time. |

Response Example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1695624081817,  
  "data": {  
    "resultList": [  
      {  
        "loanId": "1",  
        "coin": "USDT",  
        "borrowAmount": "1",  
        "borrowType": "manual_loan",  
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
| > loanId | String | ID |
| > coin | String | Borrowed coin |
| > amount | String | Borrowed amount |
| > borrowType | String | Type of borrowing auto\_loan: Auto-loan manual\_loan: manual\_loan |
| > cTime | String | Creation time, millisecond timestamp |
| > uTime | String | Update time, millisecond timestamp |
| maxId | String | Max ID of current search result |
| minId | String | Min ID of current search result, use: `idLessThan=minId` in the next query |