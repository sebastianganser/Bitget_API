# Get Debts

Frequency limit: 10c/1s (UID)

### Description[​](#description "Direct link to Description")

Get the list of repay history

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/earn/loan/debts

Request Example

```json
curl "https://api.bitget.com/api/v2/earn/loan/debts?startTime=1685957902000&endTime=1691228302423" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*******" \  
  -H "ACCESS-PASSPHRASE:*****" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

N/A

Response example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1692436610750,  
  "data": {  
    "pledgeInfos": [  
      {  
        "coin": "USDT",  
        "amount": "28826.61539642",  
        "amountUsdt": "28826.61"  
      }  
    ],  
    "loanInfos": [  
      {  
        "coin": "ETH",  
        "amount": "11.00002748",  
        "amountUsdt": "18730.85"  
      }  
    ]  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| loanInfos | String | Loan info |
| >coin | String | Coin |
| >amount | String | Amount |
| >amountUsdt | String | Amount usdt |
| pledgeInfos | String | Pledge Info |
| >coin | String | Coin |
| >amount | String | Amount |
| >amountUsdt | String | Amount usdt |