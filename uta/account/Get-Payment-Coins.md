# Get Payment Coins

### Description[​](#description "Direct link to Description")

Query payment coins.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/account/payment-coins
* Rate limit: 10/sec/UID
* Permission: UTA mgt. (read)

Request

```json
curl "https://api.bitget.com/api/v3/account/payment-coins" \  
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
    "paymentCoinList": [  
      {  
        "coin": "ETH",  
        "size": "0.12",  
        "amount": "293.5"  
      }  
    ],  
    "maxSelection": "1"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| paymentCoinList | Array | Payment coin list |
| >coin | String | Payment coin |
| >size | String | Payment coin quantity |
| >amount | String | Payment coin amount (USD) |
| maxSelection | String | Maximum number of coins that can be selected for repayment |