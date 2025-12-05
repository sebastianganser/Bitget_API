# Get Sub Deposit Address

### Description[​](#description "Direct link to Description")

Get sub deposit address

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/account/sub-deposit-address
* Rate limit: 10/sec/UID
* Permission: UTA mgt. (read)

Request

```json
curl "https://api.bitget.com/api/v3/account/sub-deposit-address?coin=usdt&subUid=11111111" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| subUid | String | Yes | Sub-account UID  - The sub-account UID can be obtained via the Sub-account List API. |
| coin | String | Yes | Coin name  - The currency name can be obtained using the Get Currency Information API. |
| chain | String | No | Chain Name  - The chain name can be obtained using the Get Currency Information API. |
| size | String | No | Deposit Quantity  - Only applies to BTC Lightning Network  - Limit range: 0.000001 - 0.01. |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1740213448866,  
  "data": {  
    "address": "0x51xxx",  
    "chain": "erc20",  
    "coin": "USDT",  
    "tag": "",  
    "url": ""  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| address | String | Deposit Address |
| chain | String | Chain Name |
| coin | String | Coin Name |
| tag | String | Tags |
| url | String | Blockchain Explorer Address |