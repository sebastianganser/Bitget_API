# Bind/Unbind UID to Risk Unit

### Description[​](#description "Direct link to Description")

Binding:

* The uid and riskUnitId belong to the same main account.
* The uid is not bound to any other risk unit.

Unbinding:

* The API key used for the call must belong to the main account or the lending-exclusive sub-account UID within the risk
  unit.
* The uid is within the risk unit and is not equal to riskUnitId.
* The uid has a zero balance, or the riskUnitId has not\_paid\_off or in\_progress loan orders.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v3/ins-loan/bind-uid
* Rate limit: 3/sec/UID
* Permission: UTA mgt. (read)

Request

```json
curl -X POST "https://api.bitget.com/api/v3/ins-loan/bind-uid" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json" \  
   -d '{"uid":"12345678","operate":"bind"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| riskUnitId | String | No | Risk Unit ID (Required for parent account calls, not required for risk unit account calls) |
| uid | String | Yes | Sub UID（limit 50 UIDS for one Risk Unit） |
| operate | String | Yes | `bind` Bind   `unbind` Unbind |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1745725444960,  
  "data": {  
    "riskUnitId": "12345678",  
    "uid": "12345678",  
    "operate": "bind"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| riskUnitId | String | Risk Unit ID |
| uid | String | Bind or unbind the UID of the sub - account to the risk unit. Bind： The UID and the riskUnitId belong to the same main account.  The UID is not bound to other risk units.  Unbind：  The API key for invoking the interface must be the UID of the exclusive sub-account for borrowing and lending within the main account or the risk unit. The UID is within the risk unit and is not equal to the riskUnitId. The assets of the UID are zero, or there are no outstanding or in-transit borrowing and lending orders for the riskUnitId. |
| operate | String | `bind` Bind   `unbind` Unbind |