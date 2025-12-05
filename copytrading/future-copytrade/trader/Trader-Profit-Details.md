# Get Profit Share Detail

Rate Limit: 5 req/sec/UID

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/copy/mix-trader/profit-details

Request Example

```json
curl "https://api.bitget.com/api/v2/copy/mix-trader/profit-details?coin=USDT&pageSize=20&pageNo=1" \  
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
| coin | String | No | Settlement currency of profit share |
| pageSize | String | No | Number of inquiries  Default: 20, maximum: 100 |
| pageNo | String | No | Current page number Default to 1. |

Response example

```json
{  
    "code": "00000",  
    "data": [  
        {  
            "coin": "usdt",  
            "profit": "0",  
            "nickName": "nickname"  
        }  
    ],  
    "msg": "success",  
    "requestTime": 1627354109502  
}
```

### Response parameters[​](#response-parameters "Direct link to Response parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| >coin | String | Settlement currency |
| >profit | String | Profit share |
| >nickName | String | Alias |