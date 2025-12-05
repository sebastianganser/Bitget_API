# Bind/Unbind Sub-account UID to Risk Unit

Rate limit: 5 req/sec/UID

### Description[​](#description "Direct link to Description")

Here’s the English translation of the provided text:

**Binding:**

* The `uid` and `riskUnitId` belong to the same main account.
* The `uid` is not bound to any other risk unit.

**Unbinding:**

* The API key used for the call must belong to the main account or a lending-exclusive sub-account UID within the risk unit.
* The `uid` is within the risk unit and is not equal to `riskUnitId`.
* The `uid` has a zero balance, or the `riskUnitId` has no outstanding or in-progress loan orders.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/spot/ins-loan/bind-uid

Request Example

```json
curl "https://api.bitget.com/api/v2/spot/ins-loan/bind-uid" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*******" \  
  -H "ACCESS-PASSPHRASE:*****" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json"  
  -d '{   
    "uid": "xxxxx",  
    "operate":"bind"  
}
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| riskUnitId | String | No | Risk Unit ID (Required for parent account calls, not required for risk unit account calls) |
| uid | String | Yes | Sub UID（limit 50 UIDS for one Risk Unit） |
| operate | String | Yes | `bind` Bind   `unbind` Unbind |

Response Example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1711697588556,  
  "data": "success"  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| code | String | Result "00000": success others: fail |