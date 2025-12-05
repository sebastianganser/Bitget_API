# Get My Followers

Rate Limit: 5 req/sec/UID

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/copy/mix-trader/config-query-followers

Request Example

```json
curl "https://api.bitget.com/api/v2/copy/mix-trader/config-query-followers?startTime=1692624281000&endTime=1693473489000&pageNo=1&pageSize=20" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*******" \  
  -H "ACCESS-PASSPHRASE:*****" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| pageNo | String | No | Page number (default: 1) |
| pageSize | String | No | Entries per page (default: 20, maximum: 100) |
| startTime | String | No | Start timestamp  Milliseconds format of timestamp Unix, e.g. 1597026383085 (The maximum time span supported is three months. The default end time is three months if no value is set for the end time. ) |
| endTime | String | No | End timestamp  Milliseconds format of timestamp Unix, e.g. 1597026383085 (The maximum time span supported is three months. The default start time is three months ago if no value is set for the start time. ) |

Response example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1684920707124,  
    "data": [  
        {  
            "accountEquity": "3434361.0097",  
            "isRemove": "yes",  
            "followerHeadPic": "",  
            "followerName": "****@***.com",  
            "followerUid": "************",  
            "followerTime": "1684920707124"  
        }  
    ]  
}
```

### Response parameters[​](#response-parameters "Direct link to Response parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| accountEquity | String | Total account assets |
| isRemove | String | Is it able to remove followers? `yes` `no` |
| followerHeadPic | String | Follower avatar |
| followerName | String | Follower alias |
| followerUid | String | Follower user ID |
| followerTime | String | Date of following (based on date of initial following) Milliseconds format of timestamp Unix, e.g. 1597026383085 |