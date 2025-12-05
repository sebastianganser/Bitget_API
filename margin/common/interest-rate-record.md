# Get the leverage interest rate

Frequency limit:10 times/1s (IP)

### Description[​](#description "Direct link to Description")

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/margin/interest-rate-record

Request

```json
curl "https://api.bitget.com/api/v2/margin/interest-rate-record?coin=BTC"  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*******" \  
   -H "ACCESS-PASSPHRASE:*****" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| coin | String | Yes | coin |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1746692917537,  
  "data": {  
    "coin": "BTC",  
    "dailyInterestRate": "0.00003000",  
    "annualInterestRate": "0.01095000",  
    "updatedTime": "1746690900381"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| coin | String | coin |
| dailyInterestRate | String | Daily interest rate Return in decimal form with 8 decimal places. |
| quoteCoin | String | Annual interest rate Return in decimal form with 8 decimal places. |
| annualInterestRate | String | update time  In Unix timestamp format in milliseconds |