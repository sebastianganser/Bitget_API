# Get Subaccount Apikey

Frequency limit:10 times/1s (User ID)

### Description[​](#description "Direct link to Description")

Only applicable for ND broker main-account

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/broker/manage/subaccount-apikey-list

Request Example

```json
curl "https://api.bitget.com/api/v2/broker/manage/subaccount-apikey-list?subUid=111222" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*" \  
  -H "ACCESS-PASSPHRASE:*" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:zh-CN" \  
  -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| subUid | String | Yes | Sub account UID |

Response Example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1695786824200,  
    "data": [  
        {  
            "subUid": "************",  
            "label": " old remark ",  
            "apiKey": "bg_********************",  
            "secretKey": "xxxxxx",  
            "permType": "readonly",  
            "permList": [  
                "spot_trade"  
            ],  
            "ipList": [  
                "127.0.0.1"  
            ]  
        }  
    ]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| subUid | String | Sub account UID |
| label | String | apikey remark |
| apikey | String | apikey |
| secretKey | String | Secret key |
| permType | String | Permission type: read\_and\_write readonly |
| permList | List<String> | Permission list: contract\_order contract\_position spot\_trade margin\_trade: spot margin trade copytrading\_trade wallet\_transfer: permType should be 'read\_and\_write' |
| ipList | List<String> | IP whitelist |