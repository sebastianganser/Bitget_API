# Get Profit Share Group by Coin & Date

Rate Limit: 5 req/sec/UID

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/copy/mix-trader/profits-group-coin-date

Request Example

```json
curl "https://api.bitget.com/api/v2/copy/mix-trader/profits-group-coin-date?pageSize=20&pageNo=1" \  
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
| pageSize | String | No | Number of inquiries  Defaults to 20 entries and supports a maximum of 50 entries. |
| pageNo | String | No | Current page number Default to 1. |

Response example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1695807225928,  
    "data": [  
        {  
            "coin": "usdt",  
            "profit": "15",  
            "profitTime": "1627354109502"  
        }  
    ]  
}
```

### Response parameters[​](#response-parameters "Direct link to Response parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| >>coin | String | Cryptocurrency |
| >>profit | String | PnL (in the dimension of the cryptocurrency and the date) |
| >>profitTime | String | Time to distribute profit share (milliseconds) (in the dimension of the cryptocurrency and the date) |