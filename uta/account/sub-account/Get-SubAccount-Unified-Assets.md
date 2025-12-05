# Get SubAccount Unified Assets

### Description[​](#description "Direct link to Description")

Get SubAccount Unified Assets

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/account/sub-unified-assets
* Rate limit: 1/sec/UID
* Unified account management read permissions are required

Request

```json
curl -X GET "https://api.bitget.com/api/v3/account/sub-unified-assets" \  
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
| subUid | String | No | Sub-account UID  Leave blank to return all sub-account asset lists |
| cursor | String | No | Cursor ID  For pagination. Omit in first request. Pass previous cursor in subsequent requests. |
| limit | String | No | Sub-accounts per Page  Default value is 10, maximum is 50. |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1751970047603,  
  "data": [  
    {  
      "subUid": "1111111111",  
      "cursor": "5832862",  
      "assets": [  
        {  
          "coin": "USDT",  
          "equity": "1",  
          "usdValue": "0.99996985",  
          "balance": "1",  
          "available": "1",  
          "debt": "0",  
          "locked": "0"  
        }  
      ]  
    }  
  ]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| subUid | String | Sub-account UID |
| assets | String | List of account coins |
| > coin | String | Asset coin |
| > equity | String | Equity of the asset coin Unit is the asset coin |
| > usdValue | String | USD value of the asset coin Unit is USD |
| > balance | String | Balance of the asset coin |
| > debt | String | Debt of the asset coin |
| > available | String | Available amount of the asset coin |
| > locked | String | Amount occupied by orders Only has value in spot order scenarios |
| cursor | String | Cursor ID |