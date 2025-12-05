# Get Cross Interest Rate and Max Borrowable

Frequency limit:10 times/1s (IP)

### Description[​](#description "Direct link to Description")

This interface will determine the user's VIP level based on the User ID sending the request, and then return information such as interest rates and limits based on the VIP level.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/margin/crossed/interest-rate-and-limit

Request Example

```json
curl "https://api.bitget.com/api/v2/margin/crossed/interest-rate-and-limit?coin=ETH"  -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*******" \  
   -H "ACCESS-PASSPHRASE:*****" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| coin | String | Yes | Trading pairs, like BTC, ETH |

Response Example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1695167748916,  
    "data": [  
        {  
            "transferable": true,  
            "leverage": "3",  
            "coin": "ETH",  
            "borrowable": true,  
            "dailyInterestRate": "0.0005",  
            "annualInterestRate": "0.05",  
            "maxBorrowableAmount": "100000",  
            "vipList": [  
                {  
                    "level":"0",  
                    "limit":"1000",  
                    "dailyInterestRate":"0.00001",  
                    "annualInterestRate":"0.01",  
                    "discountRate":"1"  
                }  
            ]  
        }  
    ]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| coin | String | Coins, such as BTC, ETH |
| leverage | String | Leverage  The default value is 3, and it has three tiers: 3, 5, and 10. |
| transferable | Boolean | Transfer supported? true: Transferable false: Not transferable |
| borrowable | Boolean | Borrowable or not? true: Borrowable false: Not borrowable |
| dailyInterestRate | String | Non-VIP daily interest rate |
| annualInterestRate | String | Non-VIP APR |
| maxBorrowableAmount | String | Maximum borrow |
| vipList | Array | VIP level |
| > level | String | VIP level |
| > limit | String | VIP limit |
| > dailyInterestRate | String | VIP daily interest rate |
| > annualInterestRate | String | VIP APR |
| > discountRate | String | VIP discount: 1 is for 100%, i.e. no discount; 0.97 is for 97% of the original rate |