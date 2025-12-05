# Cross Flash Repay

Frequency limit: 10 times/1s (UID)

### Description[​](#description "Direct link to Description")

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/margin/crossed/account/flash-repay

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/margin/crossed/account/flash-repay" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*******" \  
   -H "ACCESS-PASSPHRASE:*****" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json" \     
   -d '{"coin": "BTC"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| coin | String | No | Repayment coin for the cross margin If you don't fill it, then cross margin account will be fully repaid. |

Response Example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1695619576187,  
  "data":   
    {  
      "repayId": "3423423",  
      "coin": "ETH"  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| repayId | String | Repayment id |
| coin | String | Repayment coin. In case of full repayment, the coin will be returned with no residual value. |