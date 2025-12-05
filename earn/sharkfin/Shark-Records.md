# SharkFin Records

Frequency limit: 10c/1s (Uid)

### Description[​](#description "Direct link to Description")

Get sharkfin records

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/earn/sharkfin/records

Request Example

```json
curl "https://api.bitget.com/api/v2/earn/sharkfin/records?type=subscription" \  
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
| coin | String | No | Subscribe coin |
| type | String | Yes | Transaction type `subscription` subscription  `redemption`  `interest` interest payment |
| startTime | String | No | Start timestamp  (Copy trade creation time) Milliseconds format of timestamp Unix, e.g. 1597026383085 (The maximum time span supported is three months. The default start time is three months ago if no value is set for the start time. ) |
| endTime | String | No | End timestamp  (Copy trade creation time) Milliseconds format of timestamp Unix, e.g. 1597026383085 (The maximum time span supported is three months. The default end time is now if no value is set for the end time. ) |
| limit | String | No | Number of queries: Default: 20, maximum: 100. |
| idLessThan | String | No | Separate page content before this ID is requested (older data), and the value input should be the end ID of the last request. |

Response Example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1696757048457,  
    "data": {  
        "resultList": [  
            {  
                "orderId": "1",  
                "product": "USDT/BTC_20231013",  
                "period": "7",  
                "amount": "100.00000000",  
                "ts": "1696756278760",  
                "type": "subscription"  
            }  
        ],  
        "endId": "1"  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| resultList | List<Object> | Record list |
| > orderId | String | RecordId |
| > product | String | Sharkfin productName |
| > period | String | Investment period |
| > amount | String | Subscribe amount |
| > ts | String | Create timestamp  Milliseconds format of timestamp Unix, e.g. 1597026383085 |
| > type | String | Transaction type `subscription` subscription  `redemption`  `interest` interest payment |