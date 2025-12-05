# Isolated Flash Repay

Frequency limit: 10 times/1s (UID)

### Description[​](#description "Direct link to Description")

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/margin/isolated/account/flash-repay

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/margin/isolated/account/flash-repay" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*******" \  
   -H "ACCESS-PASSPHRASE:*****" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json" \     
   -d '{"symbolList": ["ETHUSDT"]}"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| symbolList | List | No | Trading pair array under isolated mode If it is not filled, all trading pair will be confirmed by default. Up to 100 trading pairs in one request |

Response Example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1695619576187,  
  "data": [  
    {  
      "repayId": "3423423",  
      "symbol": "ETHUSDT",  
      "result": "success"  
    }  
  ]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| repayId | String | Repayment id |
| symbol | String | Spot margin trading pairs |
| result | String | success Repayment request successful failure Failure to repay |