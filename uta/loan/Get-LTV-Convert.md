# Get LTV

### Description[​](#description "Direct link to Description")

Get LTV

1. If the riskUnitId parameter is not passed in, the account calling the interface must be an institutional exclusive lending unit account.
2. If this parameter has been provided, the UID carried in the parameter must belong to an institutional lending exclusive unit account, and the account calling the API must be the primary account.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/ins-loan/ltv-convert
* Rate limit: 3/sec/UID
* Permission: UTA mgt. (read)

Request

```json
curl "https://api.bitget.com/api/v3/ins-loan/ltv-convert?riskUnitId=xxxxxxxx" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| riskUnitId | String | No | Risk Unit ID |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1711697588556,  
  "data": {  
    "ltv": "0.6667",  
    "subAccountUids": [  
      "xxxxxxxxxx",  
      "xxxxxxxxxx"  
    ],  
    "unpaidUsdtAmount": "1.12",  
    "usdtBalance": "1223",  
    "unpaidInfo": [  
      {  
        "coin": "USDT",  
        "unpaidQty": "12",  
        "unpaidInterest": "1.2"  
      }  
    ],  
    "balanceInfo": [  
      {  
        "coin": "USDT",  
        "price": "12",  
        "amount": "1.2",  
        "convertedUsdtAmount": "12"  
      }  
    ]  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| ltv | String | Risk rate, 0.6667 |
| subAccountUids | Array | Sub-accounts user ID in Risk Unit |
| usdtBalance | String | Total assets (margin coins converted to USDT) |
| unpaidUsdtAmount | String | Total debt (converted to USDT) |
| unpaidInfo | Array | Debt details |
| > coin | String | coin |
| > unpaidQty | String | Unpaid principle |
| > unpaidInterest | String | Unpaid interest |
| balanceInfo | Array | Asset details |
| > coin | String | Margin coin |
| > price | String | Margin coin price |
| > amount | String | Margin coin equity |
| > convertedUsdtAmount | String | Margin conversion amount (converted to USDT) |