# Set Holding Mode

### Description[​](#description "Direct link to Description")

This endpoint allows you to set the position holding mode between one-way and hedge mode.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v3/account/set-hold-mode
* Rate limit: 10/sec/UID
* Permission: UTA mgt. (read & write)

Request

```json
curl -X POST "https://api.bitget.com/api/v3/account/set-hold-mode" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json" \  
   -d '{"holdMode": "one_way_mode"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| holdMode | String | Yes | Holding mode `one_way_mode` This mode allows holding positions in a single direction, either long or short, but not both at the same time  `hedge_mode` This mode allows holding both long and short positions simultaneously |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1728625799912,  
  "data": "success"  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

N/A