# Get Switch Union USDT

Rate limits: 1 time/1s (uid)

### Description[​](#description "Direct link to Description")

Get USDT quota for switching from union margin to single margin

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/mix/account/switch-union-usdt

Request

```json
curl "https://api.bitget.com/api/v2/mix/account/switch-union-usdt" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

无

Response Example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1695809161807,  
  "data": {  
    "usdtAmount": "1"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| usdtAmount | String | USDT quota required for account mode switching Unit: USDT |