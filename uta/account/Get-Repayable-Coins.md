# Get Repayable Coins

### Description[​](#description "Direct link to Description")

Query repayable coins.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/account/repayable-coins
* Rate limit: 10/sec/UID
* Permission: UTA mgt. (read)

Request

```json
curl "https://api.bitget.com/api/v3/account/repayable-coins" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

N/A

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1730189435812,  
  "data": {  
    "repayableCoinList": [  
      {  
        "coin": "USDT",  
        "size": "147214.04781004",  
        "amount": "147102.60677584"  
      }  
    ],  
    "maxSelection": "1"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| repayableCoinList | Array | Repayable coin list |
| >coin | String | Repayable coin |
| >size | String | Repayable coin quantity |
| >amount | String | Repayable coin amount (USD) |
| maxSelection | String | Maximum number of coins that can be selected for repayment |