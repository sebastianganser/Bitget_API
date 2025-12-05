# Savings Product List

Rate limit: 10 req/sec/UID

### Description[​](#description "Direct link to Description")

Get Savings Product List

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/earn/savings/product

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
| coin | String | No | Coin eg： BTC |
| filter | String | No | Filter conditions `available` Available for subscription `held` Held  `available_and_held` Available for subscription and held   `all` Query all Including those that have been removed from the shelves |

Response Example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1696747382760,  
    "data": [  
        {  
            "productId": "12313123",  
            "coin": "BGB",  
            "periodType": "flexible",  
            "period": "",  
            "apyType": "ladder",  
            "advanceRedeem": "",  
            "settleMethod": "",  
            "apyList": [  
                {  
                    "rateLevel": "0",  
                    "minStepVal": "0.000000",  
                    "maxStepVal": "200.000000",  
                    "currentApy": "6.00"  
                },  
                {  
                    "rateLevel": "1",  
                    "minStepVal": "200.000000",  
                    "maxStepVal": "5000.000000",  
                    "currentApy": "50.00"  
                }  
            ],  
            "status": "in_progress",  
            "productLevel": "normal"  
        }  
    ]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| productId | String | Product id |
| coin | String | Savings subscription coin |
| periodType | String | Period type  `flexible` flexible period  `fixed` fixed period |
| period | String | Period `flexible` This value is not returned |
| apyType | String | Interest rate type  `single` single interest rate  `ladder` ladder income |
| advanceRedeem | String | Whether early redemption is allowed  `Yes` allowed  `No` not allowed |
| settleMethod | String | Settlement method   `daily` daily interest and daily settlement   `maturity` repayment of principal and interest at maturity |
| apyList | List<Object> | Ladder interest rate information |
| > rateLevel | String | Rate level |
| > minStepVal | String | Ladder minimum amount value |
| > maxStepVal | String | Ladder maximum amount value |
| > currentApy | String | Current tiered annual interest rate |
| status | String | Product status `not_started` Warming up `in_progress` Subscribing `paused` Paused `completed` Ended `sold_out` Sold out  `off_line` Off line |
| productLevel | String | Product level  `beginner` beginner product  `normal` normal product  `VIP` VIP product |