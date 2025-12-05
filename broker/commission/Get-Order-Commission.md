# Get Order Commission

Rate limit: 20/sec/UID

### Description[​](#description "Direct link to Description")

* Data storage: 30 days
* Historical data backtracking: 2025/9/1
* Data granularity: daily
* Data update frequency: daily, previous day's data is updated on the current day
* Time zone: UTC+8
* startTime and endTime should either both be set or both not set
* The maximum time span supported for startTime and endTime is 30 days
* This API supports retrieving data within the past 30 days
* If startTime and endTime are not set in the request, the default return will be information for yesterday (00:00-23:59
  UTC+8)
* This API data is updated on a T+1 basis
* Transaction details only show those marked with broker channel id

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/broker/order-commission

Request

```json
curl "https://api.bitget.com/api/v2/broker/order-commission" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*" \  
  -H "ACCESS-PASSPHRASE:*" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| startTime | String | No | Start timestamp in milliseconds. If both startTime and endTime are empty, the default time range is yesterday 00:00–23:59 (UTC+8). startTime and endTime must either both be filled or both be empty. An error will be returned if the range exceeds 180 days. |
| endTime | String | No | End timestamp in milliseconds. If both startTime and endTime are empty, the default time range is yesterday 00:00–23:59 (UTC+8). startTime and endTime must either both be filled or both be empty. An error will be returned if the range exceeds 180 days. |
| limit | String | No | Pagination limit. Maximum: 500, Default: 500 |
| uid | String | No | UID |
| orderId | String | No | Order ID |
| idLessThan | String | No | Cursor ID for pagination. Do not pass this parameter for the first request; for subsequent requests, use the endId value from the previous response to paginate. |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1695786824200,  
  "data": {  
    "commissionlist": [  
      {  
        "fillId": "121211212122",  
        "orderId": "121211212122",  
        "ts": "1689833233282",  
        "clientOid": "121211212122",  
        "bizType": "spot",  
        "subBizType": "spot_trade",  
        "symbol": "BTCUSDT",  
        "volume": "1000",  
        "fee": "1",  
        "pureFee": "1",  
        "rebateAmount": "0.5"  
      }  
    ],  
    "endId": "12345"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| commissionlist | List | Rebate (commission) list |
| > fillId | String | Fill ID |
| > orderId | String | Order ID |
| > ts | String | Fill timestamp |
| > clientOid | String | Custom order ID |
| > bizType | String | Transaction type `spot`Spot `futures`Futures |
| > subBizType | String | Sub-transaction type `spot_trade`Spot trading `spot_margin`Spot margin `usdt_futures`usdt futures `coin_futures`coin futures `usdc_futures`usdc futures |
| > symbol | String | Symbol |
| > volume | String | Trade amount  unit: USDT, with full precision |
| > fee | String | Total fee unit: USDT, with full precision |
| > pureFee | String | Net fee unit: USDT, with full precision |
| > rebateAmount | String | Broker commission unit: USDT, with full precision |
| endId | String | Cursor ID |