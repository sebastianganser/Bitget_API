# Get Cross Tier Configuration

Frequency limit:10 times/1s (IP)

### Description[​](#description "Direct link to Description")

This interface will determine the user's VIP level based on the User ID sending the request, and then return the tier information based on the VIP level.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/margin/crossed/tier-data

Request Example

```json
curl "https://api.bitget.com/api/v2/margin/crossed/tier-data?coin=ETH"  -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*******" \  
   -H "ACCESS-PASSPHRASE:*****" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| coin | String | Yes | Coin |

Response Example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1695167748916,  
    "data": [  
        {  
            "tier": "1",  
            "leverage": "3",  
            "coin": "ETH",  
            "maxBorrowableAmount": "6",  
            "maintainMarginRate": "0.05"  
        }  
    ]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| tier | String | Tier |
| leverage | String | Effective leverage, global default: 3x |
| coin | String | Coin |
| maxBorrowableAmount | String | Maximum borrow |
| maintainMarginRate | String | Maintenance margin rate |