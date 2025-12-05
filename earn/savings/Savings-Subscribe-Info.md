# Savings Subscription Detail

Frequency limit: 10c/1s (Uid)

### Description[​](#description "Direct link to Description")

Get subscription detail before subscribe savings.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/earn/savings/subscribe-info

Request Example

```json
curl "https://api.bitget.com/api/v2/earn/savings/subscribe-info?productId=123123&periodType=flexible" \  
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
| productId | String | Yes | Product ID |
| periodType | String | Yes | Period type  `flexible` flexible period  `fixed` fixed period |

Response Example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1696751519392,  
    "data": {  
        "singleMinAmount": "10.000000",  
        "singleMaxAmount": "2000.000000",  
        "remainingAmount": "4899.999990",  
        "subscribePrecision": "6",  
        "profitPrecision": "6",  
        "subscribeTime": "1696751519451",  
        "interestTime": "1696780800000",  
        "settleTime": "1696867200000",  
        "expireTime": "",  
        "redeemTime": "",  
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
        "redeemDelay": ""  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| singleMinAmount | String | Minimum limit for a single transaction |
| singleMaxAmount | String | Maximum limit for a single transaction |
| remainingAmount | String | Amount held remaing |
| subscribePrecision | String | Subscription precision |
| profitPrecision | String | Profit precison |
| subscribeTime | String | Subscription time, Unix millisecond timestamp |
| interestTime | String | Interest generation time, Unix millisecond timestamp |
| settleTime | String | Interest settlement time, Unix millisecond timestamp |
| expireTime | String | Expiration time, Unix millisecond timestamp |
| redeemTime | String | Redemption time, Unix millisecond timestamp |
| apyList | List<Object> | Ladder interest rate info |
| > rateLevel | String | Rate level |
| > minStepVal | String | Ladder minimum amount value |
| > maxStepVal | String | Ladder maximum amount value |
| > currentApy | String | Current tiered annual interest rate |
| redeemDelay | String | The number of days of delay in the redemption’s arrival. The return value is D+1, which means the redemption is delayed by one day, and so on. |