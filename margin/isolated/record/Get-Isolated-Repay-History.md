# Get Isolated Repayment History

Frequency limit: 10 times/1s (UID)

### Description[​](#description "Direct link to Description")

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/margin/isolated/repay-history

Request Example

```json
curl "https://api.bitget.com/api/v2/margin/isolated/repay-history?symbol=BTCUSDT&startTime=1695336324000"  -H "ACCESS-KEY:*******" \  
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
| repayId | String | No | Repayment ID |
| coin | String | No | Coin |
| startTime | String | Yes | Start time, Unix millisecond timestamps |
| endTime | String | No | End time, Unix millisecond timestamps Maximum interval between start and end times is 90 days |
| limit | String | No | Number of queries Default: 100, maximum: 500 |
| idLessThan | String | No | For turning pages. No setting is needed when querying for the first time. Set to to smallest repayId returned from the last query when searching for data in the second page and other paged. Data smaller than the repayId entered will be returned. This is designed to shorten the query response time. |

Response Example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1695624627000,  
  "data": {  
    "resultList": [  
      {  
        "repayId": "1",  
        "coin": "BTC",  
        "repayAmount": "1",  
        "repayType": "manual_repay",  
        "repayInterest": "0.01",  
        "repayPrincipal": "0.99",  
        "symbol": "BTCUSDT",  
        "cTime": "1695624616058",  
        "uTime": "1695624616058"  
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
| > repayId | String | ID |
| > coin | String | Coin |
| > repayPrincipal | String | Repayment principal |
| > repayAmount | String | Total repayment |
| > repayInterest | String | Repayment interest |
| > repayType | String | Repayment type auto-repay: Automatic repayment manual-repay: Manual repayment liq-repay: Liquidation repayment force-repay: Forced repayment |
| > cTime | String | Creation time, millisecond timestamp |
| > uTime | String | Update time, millisecond timestamp |
| maxId | String | Max ID of current search result |
| minId | String | Min ID of current search result, use: `idLessThan=minId` in the next query |