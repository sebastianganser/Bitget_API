# Get Repayment Orders

Rate limit: 5 req/sec/UID

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/spot/ins-loan/repaid-history

Request Example

```json
curl "https://api.bitget.com/api/v2/spot/ins-loan/repaid-history" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*******" \  
  -H "ACCESS-PASSPHRASE:*****" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| startTime | String | No | The start timestamp (ms) |
| endTime | String | No | The end timestamp (ms) |
| limit | String | No | Limit default 100; max 100 |

Response Example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1711697588556,  
  "data": [{  
    "repayOrderId": "xxxxxxx",  
    "businessType": "normal",  
    "repayType":"all",  
    "repaidTime":"1713645576789",  
    "coin":"USDT",  
    "repaidAmount":"1",  
    "repaidInterest":"1.1"  
  }]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| repayOrderId | String | Repaid order ID |
| repaidTime | Array | Repaid timestamp (ms) |
| coin | String | Repaid coin |
| repayAmount | String | Repaid principle |
| repayInterest | String | Repaid interest |
| repayType | String | Repaid type `all`: All repayment `part`: partial repayment |
| businessType | String | Business type `normal`: normal repayment `liquidation`: repaid by liquidation |