# Switch Account

### Description[​](#description "Direct link to Description")

1. Only supports parent accounts.
2. This endpoint is only used for switching to classic account mode.
3. Please note that since the account switching process takes approximately 1 minute, the successful response you receive only indicates that the request has been received, and does not mean that the account has been successfully switched to the classic account.
4. Please use the query switching status interface to confirm whether the account switching is successful.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v3/account/switch
* Rate limit: 1/sec/UID

Request

```json
curl -X POST "https://api.bitget.com/api/v3/account/switch" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json" \  
   -d '{}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

N/A

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1728625799912,  
  "data": null  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

N/A