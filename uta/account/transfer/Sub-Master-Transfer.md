# Sub-Main Account Transfer

### Description[​](#description "Direct link to Description")

Sub-account initiates transfer to master account，and the caller must be the sub-account account API Key.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v3/account/sub-master-transfer
* Rate limit: 5/sec/UID
* Unified account management read and write permissions are required

Request

```json
curl -X POST "https://api.bitget.com/api/v3/account/sub-master-transfer" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json" \  
   -d '{"fromType":"spot","toType":"uta","amount":"1000","coin":"USDT","clientOid":"xxxxx"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| fromType | String | Yes | Transferring Account Type `spot` Funding account `uta` Unified Account |
| toType | String | Yes | Receiving Account Type `spot` Funding account `p2p` OTC account `uta` Unified Account |
| amount | String | Yes | Amount to Transfer In |
| coin | String | Yes | Transfer Currency, e.g., BTC |
| clientOid | String | No | clientOid,Cannot exceed 64 characters. |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1740213448866,  
  "data": {  
    "transferId": "172947298237423",  
    "clientOid": "test_001"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| transferId | String | transferId |
| clientOid | String | clientOid |