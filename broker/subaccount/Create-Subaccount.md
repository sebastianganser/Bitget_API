# Create Subaccount

Frequency limit: 1 time/1s (User ID)

### Description[​](#description "Direct link to Description")

Create subaccounts

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/broker/account/create-subaccount

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/broker/account/create-subaccount" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*" \  
  -H "ACCESS-PASSPHRASE:*" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:zh-CN" \  
  -H "Content-Type: application/json" \  
  -d '{"subaccountName": "subaccountName1","label": "remark"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| subaccountName | String | Yes | Subaccount name, i.e. email address |
| label | String | No | Remark, length < 20 |

Response Example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1695784054984,  
    "data": {  
        "subUid": "********",  
        "subaccountName": "***********",  
        "status": "normal",  
        "permList": [  
            "read",  
            "spot_trade",  
            "contract_trade",  
            "transfer",  
            "withdraw",  
            "deposit"  
        ],  
        "label": "old remark",  
        "cTime": "1695784057280"  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| subUid | String | Subaccount user id |
| subaccountName | String | Subaccount name |
| status | String | Subaccount Status normal  freeze  del |
| permList | List<Sting> | Permissions, separated by comma. withdraw transfer spot\_trade contract\_trade read deposit |
| label | String | Label, less than 50 characters |
| ctime | String | Creation time Unix millisecond timestamp, e.g. 1690196141868 |