# My Trader List

Rate Limit: 5 req/sec/UID

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/copy/spot-follower/query-traders

Request Example

```json
curl "https://api.bitget.com/api/v2/copy/spot-follower/query-traders" \  
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
| pageSize | String | No | The default is 20, and the maximum supported is 50. |
| startTime | String | No | start Time |
| endTime | String | No | end Time |

Response example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1695813674738,  
    "data": {  
        "resultList": [  
            {  
                "certificationType": "Uncertified",  
                "traceTotalAmount": "16027.6543",  
                "traceTotalNetProfit": "43.2480",  
                "traceTotalProfit": "52.8743",  
                "traderName": "BGU***9Z72",  
                "traderId": "**********",  
                "maxFollowLimit": "300",  
                "bgbMaxFollowLimit": "",  
                "followCount": "1",  
                "bgbFollowCount": "",  
                "followerTime": "1693533344295"  
            }  
        ]  
    }  
}
```

### Response Description[​](#response-description "Direct link to Response Description")

| Parameter | Parameter Type | Description |
| --- | --- | --- |
| certificationType | String | Certification type uncertified certified |
| traceTotalAmount | String | Cumulative position opening value in USDT |
| traceTotalNetProfit | String | Net profit in USDT |
| traceTotalProfit | String | otal profit in USDT |
| traderName | String | trader nick name |
| traderId | String | trader Id |
| maxFollowLimit | String | Maximum number of followers |
| bgbMaxFollowLimit | String | Maximum number of followers granted by BGB holdings |
| followCount | String | Number of current followers |
| bgbFollowCount | String | Number of followers granted by BGB holdings |
| followerTime | String | Following date (take the first following date) Milliseconds format of timestamp Unix, e.g. 1597026383085 |