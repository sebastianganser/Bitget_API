# Get Financial Records

### Description[​](#description "Direct link to Description")

Query financial records within the last 90 days.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/account/financial-records
* Rate limit: 20/sec/UID
* Permission: UTA mgt. (read)

Request

```json
curl "https://api.bitget.com/api/v3/account/financial-records?category=USDT-FUTURES&coin=BGB" \  
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
| category | String | Yes | Product type   `SPOT` Spot trading   `MARGIN` Margin trading   `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures   `OTHER` Other |
| coin | String | No | Coin name e.g.,`BTC` |
| type | String | No | Type `TRANSFER_IN`/`TRANSFER_OUT`...... All enumeration values can be viewed under the Enumeration category. |
| startTime | String | No | Start timestamp  A Unix timestamp in milliseconds e.g.,`1597026383085` The access window is 90 days |
| endTime | String | No | End timestamp  A Unix timestamp in milliseconds e.g.,`1597026383185`  The time range between `startTime` and `endTime` must not exceed 30 days |
| limit | String | No | Limit per page Default:`100`. Maximum:`100` |
| cursor | String | No | Cursor  Pagination is implemented by omitting the cursor in the first query and applying the cursor from the previous query for subsequent pages |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1750135478641,  
  "data": {  
    "list": [  
      {  
        "category": "Margin",  
        "id": "13111111111111111",  
        "symbol": "BTCUSDT",  
        "coin": "BTC",  
        "type": "ORDER_DEALT_IN",  
        "amount": "0.00531168",  
        "fee": "-0.00000531",  
        "balance": "55.10017801",  
        "ts": "1745853486185"  
      }  
    ],  
    "cursor": "122222222222222222"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| list | Array | List |
| >category | String | Product Type   `SPOT` Spot trading   `MARGIN` Margin trading   `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures   `OTHER` Other |
| >id | String | Record ID |
| >symbol | String | Symbol name |
| >coin | String | Coin name |
| >type | String | Type `TRANSFER_IN`/`TRANSFER_OUT`/...... All enumeration values can be viewed under the Enumeration category. |
| >amount | String | Amount |
| >fee | String | Fee |
| >balance | String | Balance |
| >ts | String | The timestamp that system generated the data A Unix millisecond timestamp. |
| cursor | String | Cursor |