# Modify Subaccount ApiKey

Rate limit: 10 req/sec/UID

### Description[​](#description "Direct link to Description")

Only applicable for ND broker main-account to modify ApiKey for the specified sub-account

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/broker/manage/modify-subaccount-apikey

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/broker/manage/modify-subaccount-apikey" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*" \  
  -H "ACCESS-PASSPHRASE:*" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:zh-CN" \  
  -H "Content-Type: application/json" \  
  -d '{"subUid": "1","passphrase": "12345678","apiKey": "xx_xxx","label": "old remark","ipList":["127.0.0.1"],"permType": "readonly","permList":["spot_trade"]}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| subUid | String | Yes | Sub account UID |
| apikey | String | Yes | Sub account API Key |
| label | String | No | remark, length < 20 |
| passphrase | String | Yes | Passphrase, please recreate if forgot |
| ipList | List<String> | No | IP whitelist, override, max 30 IP entries. Empty means no change |
| permType | String | Yes | Permission type, override. Empty means no change `read_and_write`: read and write `readonly`: read only |
| permList | List<String> | Yes | Permission list, override. Empty means not change `contract_order`: contract orders `contract_position`: contract positions `spot_trade`: spot trade `margin_trade`: spot margin trade `copytrading_trade`: copy trading trade `wallet_transfer`: wallet transfer(available when `permType` is `read_and_write`) |

Response Example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1695785738672,  
    "data": {  
        "subUid": "*********",  
        "apiKey": "bg_**********************",  
        "label": "old remark",  
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
| permType | String | Permission type read\_and\_write readonly |
| permList | List<String> | Permission list contract\_order contract\_position spot\_trade margin\_trade: spot margin trade copytrading\_trade wallet\_transfer: permType should be 'read\_and\_write' |
| ipList | List<String> | IP whitelist |