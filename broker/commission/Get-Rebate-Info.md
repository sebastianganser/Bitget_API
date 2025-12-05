# Get Rebate Info

Rate limit: 20/sec/UID

### Description[​](#description "Direct link to Description")

* Data retention: 30 days
* Real-time data

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/broker/rebate-info

Request

```json
curl "https://api.bitget.com/api/v2/broker/rebate-info?uid=123456789" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*" \  
  -H "ACCESS-PASSPHRASE:*" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| uid | String | Yes | UID |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1695786824200,  
  "data": {  
    "affiliationType": "affiliate",  
    "userLevel": "VIP7",  
    "clientSpotRebateRatio": "0.07",  
    "clientFuturesRebateRatio": "0.08"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| affiliationType | String | Type of rebate relationship `affiliate`Client channel `official` Official (website) channel |
| userLevel | String | User level `VIP0` `VIP1` ... `VIP7` `PRO1` ... `PRO6` |
| clientSpotRebateRatio | String | Spot trading rebate ratio available to the user |
| clientFuturesRebateRatio | String | Futures trading rebate ratio available to the user |