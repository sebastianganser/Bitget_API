# Get Cross Liquidation Orders

Frequency limit:10 times/1s (UID)

### Description[​](#description "Direct link to Description")

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/margin/crossed/liquidation-order

Request Example

```json
curl "https://api.bitget.com/api/v2/margin/crossed/liquidation-order?startTime=1704100405000&endTime=1706174005091&limit=20" \  
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
| type | String | No | Type `swap`: swap   `place_order`: place order(default) |
| symbol | String | No | Trading pairs, like BTCUSDT   This field only takes effect when `type=place_order`   Default all symbols |
| fromCoin | String | No | Swap from coin   This field only takes effect when `type=swap` |
| toCoin | String | No | Swap to coin   This field only takes effect when `type=swap` |
| startTime | String | No | Start time, Unix millisecond timestamp |
| endTime | String | No | End time, Unix millisecond timestamp Maximum interval between start time and end time is 90 days |
| limit | String | No | Number of quiries Default: 100, maximum: 500 |
| idLessThan | String | No | For turning pages. The first query is not passed. When querying data in the second page and the data beyond, the last endId returned in the last query is used, and the result will return data with a value less than this one; the query response time will be shortened. |

Response Example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1708654712083,  
    "data": {  
        "resultList": [  
            {  
                "symbol": "BTCUSDT",  
                "orderType": "market",  
                "side": "liquidation-sell",  
                "priceAvg": "43024.762472",  
                "price": "43024.762472",  
                "fillSize": "1",  
                "size": "1",  
                "amount": "43024.762472",  
                "orderId": "xxxx",  
                "fromCoin": "",  
                "toCoin": "",  
                "fromSize": "",  
                "toSize": "",  
                "cTime": "1705474028200",  
                "uTime": "1705474028398"  
            }  
        ],  
        "idLessThan": "1131405566368010241"  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| orderId | String | Order no. |
| symbol | String | Trading pair   This field only takes effect when `type=place_order` |
| orderType | String | Order type  market: market price   This field only takes effect when `type=place_order` |
| side | String | Direction liquidation\_sell: Settlement – sell liquidation\_buy: Settlement – buy   This field only takes effect when `type=place_order` |
| priceAvg | String | Filled price   This field only takes effect when `type=place_order` |
| price | String | Order price   This field only takes effect when `type=place_order` |
| fillSize | String | Filled quantity   This field only takes effect when `type=place_order` |
| size | String | Order quantity   This field only takes effect when `type=place_order` |
| amount | String | Filled amount   This field only takes effect when `type=place_order` |
| fromCoin | String | Conversion source currency   This field only takes effect when `type=swap` |
| fromSize | String | The size of conversion source currency   This field only takes effect when `type=swap` |
| toCoin | String | Conversion target currency   This field only takes effect when `type=swap` |
| toSize | String | The size of conversion target currency   This field only takes effect when `type=swap` |
| cTime | String | Creation time |
| uTime | String | Updated time |