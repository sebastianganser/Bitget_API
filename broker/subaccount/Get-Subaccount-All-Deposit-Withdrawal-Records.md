# Get Sub-accounts Deposit and Withdrawal Records

Rate limit:5 req/sec/UID

### Description[​](#description "Direct link to Description")

Only applicable for ND broker main-account.

It`s able to get ND sub-accounts deposit and withdrawal records within **90 days**

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/broker/all-sub-deposit-withdrawal

Request Example

```json
curl "https://api.bitget.com/api/v2/broker/all-sub-deposit-withdrawal?startTime=1700561435000&endTime=1703153435933" \  
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
| startTime | String | No | Start timestamp  Milliseconds format of timestamp Unix, e.g. 1597026383085 If both start time and end time are empty, the default query time range will be yesterday from 00:00 to 23:59 (UTC+0) Start time and end time must either both be provided or both be empty An error will be reported if the time range exceeds 7 days |
| endTime | String | No | End timestamp  Milliseconds format of timestamp Unix, e.g. 1597026383085 If both start time and end time are empty, the default query time range will be yesterday from 00:00 to 23:59 (UTC+0) Start time and end time must either both be provided or both be empty An error will be reported if the time range exceeds 7 days |
| limit | String | No | Number of data Default: 100, maximum: 100 100 entries will be returned by default when limit is over 100 |
| idLessThan | String | No | Separate page content |
| type | String | No | Records type `all`: Both of deposit and withdrawal records(*default*) `deposit`: Deposit records `withdrawal`: Withdrawal records |

Response Example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1689833233282,  
    "data": {  
      "list": [  
        {  
          "uid": "XXXXX",  
          "txId": "XXXXXXX",  
          "type": "deposit",  
          "subType": "onchain",  
          "coin": "USDT",  
          "amount": "10",  
          "status": "success",  
          "ts": "123123"  
        }],  
      "endId": "12345"  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| uid | String | Sub-account User ID |
| txId | String | Deposit or withdrawal txId |
| coin | String | Coin name |
| type | String | Deposit or withdrawal type `deposit`: Deposit records `withdrawal`: Withdrawal records |
| subType | String | Deposit or withdrawal sub-type `onchain`: Deposit on chain or Normal withdrawal `internal`: Internal transfer `fast`: Fast deposit or withdrawal |
| amount | String | Deposit or withdrawal amount |
| status | String | Status `pending`: Pending preliminary examination `fail`: Failed `success`: Success |
| ts | String | Deposit or withdrawal update time, Unix ms |
| endId | String | Used for paginating |