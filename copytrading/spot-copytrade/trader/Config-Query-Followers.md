# My Follower List

Limit rule 10 times/1s (uid)

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/copy/spot-trader/config-query-followers

Request Example

```json
curl "https://api.bitget.com/api/v2/copy/spot-trader/config-query-followers" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*******" \  
  -H "ACCESS-PASSPHRASE:*****" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json"
```

### Request Parameter[​](#request-parameter "Direct link to Request Parameter")

| Parameter Name | Parameter Type | Required | Description |
| --- | --- | --- | --- |
| pageNo | String | No | pageNo (default 1) |
| pageSize | String | No | pageSize(default 30 max 1000) |
| startTime | String | No | start time |
| endTime | String | No | end time |

Response example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1695807814833,  
    "data": [  
        {  
            "accountEquity": "1001711.2164",  
            "isRemove": "NO",  
            "followerHeadPic": null,  
            "followerName": "BGU***1QK5",  
            "followerUid": "**********",  
            "followerTime": "1693533344295"  
        }  
    ]  
}
```

### Response Description[​](#response-description "Direct link to Response Description")

| Parameter | Parameter Type | Description |
| --- | --- | --- |
| accountEquity | String | Account asset value |
| isRemove | String | Is it able to remove followers? yes: yes; no: no |
| followerHeadPic | String | Follower avatar |
| followerName | String | Follower Nickname |
| followerUid | String | Follower user id |
| followerTime | String | Following date (take the first following date) Unix timestamp in milliseconds format, e.g. 1597026383085 |