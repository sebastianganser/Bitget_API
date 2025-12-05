# Get Broker Trade Volume

Rate limit: 5 req/sec/UID

### Description[​](#description "Direct link to Description")

* Please contact your BD or RM to apply for access permissions

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/broker/trade-volume

Request

```json
curl "https://api.bitget.com/api/v2/broker/trade-volume?startTime=1720163600000&endTime=1720663600000&pageSize=1&pageNo=1" \  
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
  "requestTime": 1720841112418,  
  "data": [  
    {  
      "uid": "5647948008",  
      "volume": "99322.66476",  
      "spotVolume": "310.66476",  
      "futureVolume": "99012"  
    }  
  ]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| uid | String | User ID |
| volume | String | Transaction amount, with 8 digits of precision |
| spotVolume | String | Spot transaction amount, with 8-digit precision |
| futureVolume | String | Contract transaction amount, with 8-digit precision |