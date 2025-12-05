# Create Subaccount ApiKey

Frequency limit:10 times/1s (User ID)

### Description[​](#description "Direct link to Description")

Only applicable for ND broker main-account

Create ApiKey for the specified subaccount

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/broker/manage/create-subaccount-apikey

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/broker/manage/create-subaccount-apikey" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*" \  
  -H "ACCESS-PASSPHRASE:*" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:zh-CN" \  
  -H "Content-Type: application/json" \  
  -d '{"subUid": "12345678","passphrase": "12345678","label": " old remark ","ipList":["127.0.0.1"],"permType": "readonly","permList":["spot_trade"]}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| subUid | String | Yes | Sub account UID |
| passphrase | String | Yes | Passphrase, length between 6 and 32 |
| label | String | Yes | remark, length < 20 |
| ipList | List<String> | Yes | IP whitelist, max 30 IP entries it's optional when `permType` is `readonly` |
| permType | String | Yes | Permission type `read_and_write` `readonly` |
| permList | List<String> | Yes | Permission list contract\_order contract\_position spot\_trade margin\_trade: spot margin trade copytrading\_trade wallet\_transfer: `permType` should be `read_and_write` |

Response Example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1695785738672,  
    "data": {  
        "subUid": "1",  
        "apiKey": "xx_xxx",  
        "secretKey": "xxxxxx",  
        "label": " old remark ",  
        "ipList":["127.0.0.1"],  
        "permType": "readonly",  
        "permList":["spot_trade"]  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| subUid | String | Sub account UID |
| label | String | apikey remark |
| apikey | String | apikey |
| secretKey | String | Secret key |
| permType | String | Permission type read\_and\_write readonly |
| permList | List<String> | Permission list contract\_order contract\_position spot\_trade margin\_trade: spot margin trade copytrading\_trade wallet\_transfer: permType should be 'read\_and\_write' |
| ipList | List<String> | IP whitelist |