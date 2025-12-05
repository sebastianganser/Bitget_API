# Get Convert Records

### Description[​](#description "Direct link to Description")

Query convert records within the last 90 days.

### HTTP request[​](#http-request "Direct link to HTTP request")

* GET /api/v3/account/convert-records
* Rate limit: 20/sec/UID
* Permission: UTA mgt. (read)

请求示例

```json
curl "https://api.bitget.com/api/v3/account/convert-records?fromCoin=BTC&toCoin=USDT" \  
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
| fromCoin | String | Yes | From coin (source coin)  It refers to the coin being converted |
| toCoin | String | Yes | To coin (target coin)  It refers to the coin being converted into (received) |
| startTime | String | No | Start timestamp  A Unix timestamp in milliseconds e.g.,`1597026383085` The access window is 90 days |
| endTime | String | No | End timestamp  A Unix timestamp in milliseconds e.g.,`1597026383185`  The time range between `startTime` and `endTime` must not exceed 30 days |
| limit | String | No | Limit per page Default:`100`. Maximum:`100` |
| cursor | String | No | Cursor  Pagination is implemented by omitting the cursor in the first query and applying the cursor from the previous query for subsequent pages |

Response

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1730369634178,  
    "data": {  
        "list": [  
            {  
                "fromCoin": "USDT",  
                "fromCoinSize": "281.72276656",  
                "toCoin": "ETH",  
                "toCoinSize": "0.0986029682",  
                "price": "0.0003499",  
                "ts": "1730359119358"  
            },  
            {  
                "fromCoin": "USDT",  
                "fromCoinSize": "3305.13434913",  
                "toCoin": "ETH",  
                "toCoinSize": "1.1567970221",  
                "price": "0.00035",  
                "ts": "1730359063138"  
            }  
        ],  
        "cursor": "1235780967957364737"  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameters | Type | Description |
| --- | --- | --- |
| list | Array | List |
| >fromCoin | String | From coin (source coin)  It refers to the coin being converted |
| >fromCoinSize | String | From coin quantity |
| >toCoin | String | To coin (target coin) It refers to the coin being converted into (received) |
| >toCoinSize | String | To coin quantity |
| >price | String | Conversion price |
| >ts | String | The timestamp of conversion A Unix millisecond timestamp |
| cursor | String | Cursor |