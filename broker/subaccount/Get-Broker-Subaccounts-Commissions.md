# Get Broker Subaccounts Commissions

Rate limit: 5 req/sec/UID

### Description[​](#description "Direct link to Description")

* Please contact your BD or RM to apply for access permissions

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/broker/commissions

Request

```json
curl "https://api.bitget.com/api/v2/broker/commissions?startTime=1720163600000&endTime=1720663600000&pageSize=1&pageNo=1" \  
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
| bizType | String | No | Optional, business type  - `spot`  - `futures`   If not filled, all types of commission information will be returne |
| subBizType | String | No | Optional, business subtype  - `spot_trade`  - `spot_margin`  - `usdt_futures`  - `usdc_futures`  - `coin_futures`  - - When `bizType=spot`, this parameter can be filled with `spot_trade` and `spot_margin` - - When `bizType=future`, this parameter can be filled with `usdt_future`, `usdc_future` and `coin_future` |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1720750077022,  
  "data": [  
    {  
      "uid": "564xxx8008",  
      "coin": "BTC",  
      "symbol": "BTC/USDT",  
      "dealtAmount": "199.81724",  
      "totalFee": "0.00000768",  
      "deductedFee": "0",  
      "paidFee": "0.00000768",  
      "markUpFee": "0.00000603",  
      "totalCommission": "0.00000686"  
    }  
  ]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| uid | String | User ID |
| coin | String | Commission coin |
| symbol | String | symbol |
| dealtAmount | String | Transaction amount |
| totalFee | String | Total Fee |
| deductedFee | String | Deduction of handling fee |
| paidFee | String | Actual paid handling fee |
| markUpFee | String | Add some handling fee |
| totalCommission | String | Total Commission |