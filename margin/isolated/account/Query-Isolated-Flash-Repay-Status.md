# Query Isolated Flash Repayment Result

Frequency limit: 10 times/1s (UID)

### Description[​](#description "Direct link to Description")

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/margin/isolated/account/query-flash-repay-status

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/margin/isolated/account/query-flash-repay-status" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*******" \  
   -H "ACCESS-PASSPHRASE:*****" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json" \     
   -d '{"idList": ["13423423"]}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| idList | List | Yes | Repayment ID list under isolated mode Up to 100 trading pairs in one request |

Response Example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 163123213132,  
  "data": [  
    {  
      "repayId": "13423423",  
      "status": "FINISH"  
    }  
  ]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| repayId | String | Repayment ID |
| status | String | Repayment result status |