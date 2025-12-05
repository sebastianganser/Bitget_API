# Get Broker Subaccounts

Rate limit: 5 req/sec/UID

### Description[​](#description "Direct link to Description")

* Please contact your BD or RM to apply for access permissions

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/broker/subaccounts

Request

```json
curl "https://api.bitget.com/api/v2/broker/subaccounts?startTime=1720163600000&endTime=1720663600000&pageSize=1&pageNo=1" \  
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
| startTime | String | No | Start timestamp, milliseconds. If both start and end time are empty, the default time is yesterday 00:00-23:59 (UTC+0). StartTime and endTime can only be filled in at the same time or not. If it exceeds 30 days, an error will be reported. |
| endTime | String | No | End timestamp, milliseconds. If both start and end time are empty, the default time is yesterday 00:00-23:59 (UTC+0). StartTime and endTime can only be filled in at the same time or not. If it exceeds 30 days, an error will be reported. |
| pageSize | String | No | Number of items per page, default is 100, maximum is 1000, if more than 1000 items are returned, 100 items will be returned by default |
| pageNo | String | No | Pagination page number, default is 1 |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1720841021439,  
  "data": [  
    {  
      "uid": "5647948008",  
      "asset": "5000.0001",  
      "firstTimeDeposit": "1720497029245",  
      "firstTimeTrade": "1720492699403",  
      "registerTime": "1720492699403"  
    }  
  ]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| uid | String | User ID |
| asset | String | Asset volume, U calculation |
| firstTimeDeposit | String | First recharge time, Unix millisecond timestamp |
| firstTimeTrade | String | First transaction time, Unix millisecond timestamp |
| registerTime | String | Registration time, Unix millisecond timestamp |