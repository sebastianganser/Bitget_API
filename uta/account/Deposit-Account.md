# Set Up Deposit Account

### Description[​](#description "Direct link to Description")

This configuration item remains valid for a long time. That is, once a user sets a default recharge account for a
certain symbol, it will be retained permanently, and there is no need to reconfigure it.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v3/account/deposit-account
* Rate limit: 1次/秒/UID
* Permission: UTA mgt. (read & write)

Request

```json
curl -X POST "https://api.bitget.com/api/v3/account/deposit-account" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json" \  
   -d '{"coin":"BTC","accountType":"funding"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| coin | String | Yes | Recharge coin  如`BTC` |
| accountType | String | Yes | Account type `funding` Funding account  `unified` Unified account `otc` OTC account The current default is the funding account, and it can be modified to a unified account or an OTC account |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1753848186558,  
  "data": "success"  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

N/A