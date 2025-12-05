# Get Isolated Order Fills

Frequency limit: 10 times/1s (UID)

### Description[​](#description "Direct link to Description")

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/margin/isolated/fills

Request Example

```json
curl "https://api.bitget.com/api/v2/margin/isolated/fills?symbol=ETHUSDT&startTime=1695336324000"  -H "ACCESS-KEY:*******" \  
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
| orderId | String | No | Order ID |
| idLessThan | String | No | Match order ID. A parameter for paging. No setting is needed when querying for the first time. Set to to smallest orderId returned from the last query when searching for data in the second page and other paged. Data smaller than the orderId entered will be returned. This is designed to shorten the query response time. |
| startTime | String | Yes | Start time, Unix millisecond timestamps |
| endTime | String | No | End time, Unix millisecond timestamps Maximum interval between start and end times is 90 days |
| limit | String | No | Number of queries Default: 100, maximum: 500 |

Response Example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1695623797791,  
  "data": {  
    "fills": [  
      {  
        "orderId": "121211212122",  
        "tradeId": "121211212122",  
        "orderType": "limit",  
        "side": "buy",  
        "priceAvg": "1721.5",  
        "size": "0.1",  
        "amount": "172.15",  
        "tradeScope": "taker",  
        "feeDetail": {  
          "deduction": "no",  
          "feeCoin": "ETH",  
          "totalDeductionFee": "0",  
          "totalFee": "-0.00010000"  
        },  
        "cTime": "1695621005237",  
        "uTime": "1695621006149"  
      }  
    ],  
    "minId": "1",  
    "maxId": "1"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| fills | List | List |
| > orderId | String | Order no. |
| > tradeId | String | Order details ID |
| > orderType | String | Order type limit market |
| > size | String | Filled quantity |
| > priceAvg | String | Filled price |
| > amount | String | Filled quantity |
| > side | String | Direction sell: Sell buy: Buy |
| > tradeScope | String | Trader tag taker maker |
| > cTime | String | Creation time, millisecond timestamp |
| > uTime | String | Update time, millisecond timestamp |
| > feeDetail | Array | Transaction fee breakdown |
| >> deduction | String | Discount or not |
| >> feecoinCode | String | Transaction fee currency |
| >> totalDeductionFee | String | Total transaction fee discount |
| >> totalFee | String | Total transaction fee |
| maxId | String | Max ID of current search result |
| minId | String | Min ID of current search result, use: `idLessThan=minId` in the next query |