# Get Discount Rate

### Description[​](#description "Direct link to Description")

Query discount rate applied to margin loans.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/market/discount-rate
* Rate limit: 20/sec/IP

Request

```json
curl "https://api.bitget.com/api/v3/market/discount-rate" \
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

N/A

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1730911874605,  
  "data": [  
      {  
        "coin": "ETH",  
        "list": [  
          {  
            "tierStartValue": "0",  
            "discountRate": "0.99"  
          },  
          {  
            "tierStartValue": "40000",  
            "discountRate": "0.98"  
          }  
        ]  
      }  
    ]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| coin | String | Coin name e.g.,`BTC` |
| list | Array | List |
| >tierStartValue | String | Tier start value   e.g., [0,10000 U）: `tierStartValue=0` [10000 U,20000 U）: `tierStartValue=10000` [20000 U,∞）: `tierStartValue=20000` |
| >discountRate | String | Discount rate |