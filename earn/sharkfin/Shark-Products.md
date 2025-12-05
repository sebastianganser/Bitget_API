# Sharkfin Products

Frequency limit: 10c/1s (Uid)

### Description[​](#description "Direct link to Description")

Get sharkfin products

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/earn/sharkfin/product

Request Example

```json
curl "https://api.bitget.com/api/v2/earn/sharkfin/product?limit=20&coin=ETH" \  
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
| coin | String | Yes | Shark coin |
| limit | String | No | Number of queries: Default: 20, maximum: 100. |
| idLessThan | String | No | Separate page content before this ID is requested (older data), and the value input should be the end ID of the last request. |

Response Example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1696754489003,  
    "data": {  
        "resultList": [  
            {  
                "productId": "1",  
                "productName": "USDT/ETH_20231009",  
                "productCoin": "ETH",  
                "subscribeCoin": "USDT",  
                "farmingStartTime": "1696744800000",  
                "farmingEndTime": "1696831200000",  
                "lowerRate": "7.06",  
                "defaultRate": "7",  
                "upperRate": "8.8",  
                "period": "7",  
                "interestStartTime": "1696838400000",  
                "status": "in_progress",  
                "minAmount": "0.1",  
                "limitAmount": "500001.0",  
                "soldAmount": "310187.2",  
                "endTime": "1696831200000",  
                "startTime": "1696744800000"  
            }  
        ],  
        "endId": "1"  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| resultList | List<Object> | Sharkfin product list info |
| >productId | String | Product ID |
| >productName | String | Sharkfin product name |
| >productCoin | String | Sharkfin product coin |
| >subscribeCoin | String | Sharkfin Subscribe coin |
| >farmingStartTime | String | Start time, Unix millisecond timestamp |
| >farmingEndTime | String | End time, Unix millisecond timestamp |
| >lowerRate | String | Minimum rate |
| >defaultRate | String | Default rate |
| >upperRate | String | Maximum rate |
| >period | String | Investment period |
| >interestStartTime | String | Interest calculation start time |
| >status | String | Product status `not_started` Warming up `in_progress` Subscribing `paused` Paused  `interest_pending` Interest is accruing  `settle_pending` Pending settlement `settled` Settled  `redeemed` redeemed   `sold_out` Sold out |
| >minAmount | String | Product minimum limit |
| >limitAmount | String | Product limit   If there is no limit, return `unlimited` |
| >soldAmount | String | Sold amount |
| >startTime | String | Start timestamp  Milliseconds format of timestamp Unix, e.g. 1597026383085 |
| >endTime | String | End timestamp  Milliseconds format of timestamp Unix, e.g. 1597026383085 |