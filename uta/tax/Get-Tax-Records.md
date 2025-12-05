# Get Unified Account Tax Records

### Description[​](#description "Direct link to Description")

Data query range: 366 days

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/tax/records
* Rate limit: 1/sec/UID
* Please use the tax API Key to request [Creation Portal](https://www.bitget.com/taxes-api)

Request

```json
curl "https://api.bitget.com/api/v3/tax/records?bizType=spot&startTime=1763402983000&endTime=1763662183573" \  
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
| bizType | String | Yes | Product type   `SPOT` Spot trading   `MARGIN` Margin trading   `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures   `OTHER` Other |
| marginType | String | No | Margin Type: `isolated` isolated margin `crossed` cross margin. This field is effective when `category=MARGIN`. If not specified, the default is `crossed` (cross margin). |
| coin | String | No | Coin name  - If not specified, tax records for all coins will be returned. |
| startTime | String | Yes | Start timestamp  A Unix timestamp in milliseconds e.g.,`1597026383085` |
| endTime | String | Yes | End timestamp  A Unix timestamp in milliseconds e.g.,`1597026383185`  The time range between `startTime` and `endTime` must not exceed 7 days |
| limit | String | No | Limit per page Default:`500`. Maximum:`500` |
| cursor | String | No | Cursor ID  - Used for pagination. Do not include it for the first query.  When querying the second page and subsequent data, use the `id` returned from the previous query. The interface will then return the data for the next page. |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1763688181556,  
  "data": [  
    {  
      "id": "1375573238088888369",  
      "coin": "USDT",  
      "type": "ORDER_DEALT_FROZEN_OUT",  
      "amount": "-1.9998656",  
      "fee": "0",  
      "balance": "42.41856383400698",  
      "ts": "1763688137552"  
    },  
    {  
      "id": "1375573238088888368",  
      "coin": "BGB",  
      "type": "ORDER_PLF_FEE_OUT",  
      "amount": "-0.0004556178732628",  
      "fee": "0",  
      "balance": "2.1598531923916739",  
      "ts": "1763688137552"  
    },  
    {  
      "id": "1375573238088888367",  
      "coin": "BGB",  
      "type": "ORDER_DEALT_IN",  
      "amount": "0.5696",  
      "fee": "0",  
      "balance": "2.1603088102649367",  
      "ts": "1763688137552"  
    }  
  ]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| id | String | Tax record id |
| coin | String | Coin name |
| type | String | Tax Type   Refer to the [Enumeration](https://www.bitget.com/api-doc/uta/enum) page for detailed types. |
| amount | String | Amount - The unit is`coin` |
| fee | String | Fee  - The unit is`coin` |
| balance | String | Balance  - The unit is`coin` |
| ts | String | The timestamp that system generated the data A Unix millisecond timestamp. |