# Savings Records

Frequency limit: 10c/1s (Uid)

### Description[​](#description "Direct link to Description")

Get savings records

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/earn/savings/records

Request Example

```json
curl "https://api.bitget.com/api/v2/earn/savings/product?filter=available_and_held" \  
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
| periodType | String | Yes | Period type  `flexible` flexible current  `fixed` fixed term |
| orderType | String | No | Record type   `subscribe` subscription   `redeem` redemption   `pay_interest` interest payment   `deduction` penalty interest (only supports regular periods) |
| startTime | String | No | Start timestamp  (Copy trade creation time) Milliseconds format of timestamp Unix, e.g. 1597026383085 (The maximum time span supported is three months. The default end time is three months if no value is set for the end time. ) |
| endTime | String | No | End timestamp  (Copy trade creation time) Milliseconds format of timestamp Unix, e.g. 1597026383085 (The maximum time span supported is three months. The default start time is three months ago if no value is set for the start time. ) |
| limit | String | No | Number of queries: Default: 20, maximum: 100. |
| idLessThan | String | No | Separate page content before this ID is requested (older data), and the value input should be the end ID of the last request. |

Response example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1696749517654,  
    "data": {  
        "resultList": [  
            {  
                "orderId": "123123123123",  
                "coinName": "BGB",  
                "settleCoinName": "BGB",  
                "productType": "flexible",  
                "period": "",  
                "productLevel": "normal",  
                "amount": "200.000000",  
                "ts": "1695797014392",  
                "orderType": "redeem"  
            }  
        ],  
        "endId": "456456456456"  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| resultList | List<Object> | Data list |
| > orderId | String | Record id |
| > coinName | String | Product Subscribe coin |
| > settleCoinName | String | Settled coin |
| > period | String | Duration `flexible` This value is not returned |
| > productLevel | String | Product level  `beginner` beginner product  `normal` normal product  `VIP` VIP product |
| > amount | String | Subscribe amount |
| > ts | String | Subscribe time timestamp |
| > orderType | String | Record type   `subscribe` subscription   `redeem` redemption   `pay_interest` interest payment   `deduction` penalty interest (only supports regular periods) |