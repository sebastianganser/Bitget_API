# Get Cross Order Fills

Frequency limit:10 times/1s (UID)

### Description[​](#description "Direct link to Description")

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/margin/crossed/fills

Request Example

```json
curl "https://api.bitget.com/api/v2/margin/crossed/fills?symbol=BTCUSDT&limit=20&startTime=1693205171000&endTime=1694155571000" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*******" \  
   -H "ACCESS-PASSPHRASE:*****" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json" \
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| symbol | String | Yes | Trading pairs, like BTCUSDT |
| orderId | String | No | Order ID |
| idLessThan | String | No | Match order ID, relative parameters of turning pages. The first query is not passed. When querying data in the second page and the data beyond, the last fillId returned in the last query is used, and the result will return data with a value less than this one; the query response time will be shortened. |
| startTime | String | Yes | Start time, Unix millisecond timestamp |
| endTime | String | No | End time, Unix millisecond timestamp Maximum interval between start time and end time is 90 days |
| limit | String | No | Number of quiries Default: 100, maximum: 500 |

Response Example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1695636829522,  
    "data": {  
        "fills": [  
            {  
                "orderId": "121211212122",  
                "tradeId": "121211212122",  
                "orderType": "limit",  
                "side": "buy",  
                "priceAvg": "32111",  
                "size": "0.01",  
                "amount": "1000",  
                "tradeScope": "taker",  
                "cTime": "1695629859821",  
                "uTime": "1695629890839",  
                "feeDetail": {  
                        "deduction": "yes",  
                        "feeCoin": "BGB",  
                        "totalDeductionFee": "-0.017118519726",  
                        "totalFee": "-0.017118519726"  
                    }  
            }  
        ],  
        "maxId": "121211212122",  
        "minId": "121211212122"  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| symbol | String | Trading pair |
| orderId | String | Order no. |
| tradeId | String | Transaction detail ID |
| size | String | Filled quantity |
| priceAvg | String | Order price |
| amount | String | Filled quantity |
| side | String | Direction sell: Sell buy: Buy liquidation\_buy: Settlement – buy liquidation\_sell: Settlement – sell system\_repay\_buy: Repay by system – buy system\_repay\_sell: Repay by system – sell |
| orderType | String | Order type limit: limit price market: market price |
| tradeScope | String | Trader tag taker: Taker maker: Maker |
| cTime | String | Creation time, millisecond timestamp |
| uTime | String | Update time, millisecond timestamp |
| feeDetail | Array | Transaction fee details |
| > deduction | String | Discount or not |
| > feecoinCode | String | Coin for transaction fee |
| > totalDeductionFee | String | Total discounted transaction fee |
| > totalFee | String | Total transaction fee |