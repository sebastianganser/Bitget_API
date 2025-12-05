# Get Broker Info

Frequency limit：10 times/1s (User ID)

### Description[​](#description "Direct link to Description")

Get account information of ND Brokers

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/broker/account/info

Request Example

```json
curl "https://api.bitget.com/api/v2/broker/account/info" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*" \  
  -H "ACCESS-PASSPHRASE:*" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

N/A

Response Example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1695783465795,  
    "data": {  
        "subAccountSize": "9",  
        "maxSubAccountSize": "10",  
        "uTime": "1691635508000"  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| subAccountSize | String | Number of sub-accounts created by the broker |
| maxSubAccountSize | String | Maximum number of sub-accounts that could be created |
| utime | String | Update time Unix millisecond timestamp, e.g. 1690196141868 |