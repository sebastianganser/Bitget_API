# Change Global Copy Trade Setting

Rate Limit: 5 req/sec/UID

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/copy/mix-trader/config-settings-base

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/copy/mix-trader/config-settings-base" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*******" \  
  -H "ACCESS-PASSPHRASE:*****" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json" \  
  -d '{"enable": "yes","showTotalEquity": "yes","showTpsl": "yes"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| enable | String | No | One of the three must be passed. Activates elite trading or not?  `YES`   `NO` |
| showTotalEquity | String | No | One of the three must be passed. Displays total assets (USDT) or not?  `YES`   `NO` |
| showTpsl | String | No | One of the three must be passed. TP/SL price of orders will be displayed publicly.  `YES`   `NO` |

Response example

```json
{  
    "code": "00000",  
    "data": "success",  
    "msg": "success",  
    "requestTime": 1627354109502  
}
```

### Response parameters[​](#response-parameters "Direct link to Response parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| data | String | Success or not |