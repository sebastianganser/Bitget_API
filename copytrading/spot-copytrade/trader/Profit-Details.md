# Get Unrealized Profit Sharing Details

Rate Limit: 5 req/sec/UID

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/copy/spot-trader/profit-details

Request Example

```json
curl "https://api.bitget.com/api/v2/copy/spot-trader/profit-details" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*******" \  
  -H "ACCESS-PASSPHRASE:*****" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json"
```

### Request Parameter[​](#request-parameter "Direct link to Request Parameter")

| Parameter Name | Parameter Type | Required | Description |
| --- | --- | --- | --- |
| coin | String | no | Settlement currency of profit share |
| pageNo | String | no | page no |
| pageSize | String | no | The number of queries  The default is 20, and the maximum supported is 50. |

Response example

```json
{  
    "code": "00000",  
    "data": [  
        {  
            "distributeRatio": "11.11",  
            "coin": "usdt",  
            "profit": "0",  
            "followerName": "bitget"  
        }  
    ],  
    "msg": "success",  
    "requestTime": 1627354109502  
}
```

### Response Description[​](#response-description "Direct link to Response Description")

| Parameter | Parameter Type | Description |
| --- | --- | --- |
| >distributeRatio | List | Profit share ratio  If the value is 11.11, it represents 11.11% |
| >profit | String | PnL |
| >coin | String | Settlement currency |
| >followerName | String | Elite trader alias |