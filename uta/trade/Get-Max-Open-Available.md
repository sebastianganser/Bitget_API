# Get Max Open Available

### Description[​](#description "Direct link to Description")

Get max open available

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v3/account/max-open-available
* Rate limit: 5/sec/UID
* Permission: UTA trade (read)

Request

```json
curl -X POST "https://api.bitget.com/api/v3/trade/max-open-available" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*" \  
  -H "ACCESS-PASSPHRASE:*" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:zh-CN" \  
  -H "Content-Type: application/json" \  
  -d '{"category":"SPOT","symbol":"BTCUSDT","orderType":"market","side":"sell"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| category | String | Yes | Product type   `SPOT` Spot trading   `MARGIN` Margin trading   `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures |
| symbol | String | Yes | Symbol name  e.g.,`BTCUSDT` |
| orderType | String | Yes | Order type `limit`/`market` |
| side | String | Yes | Transaction direction `buy`/`sell` |
| price | String | No | Order price  This field is required when orderType is `limit` |
| size | String | No | Order quantity, base coin |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1741851607871,  
  "data": {  
    "available": "52.008255",  
    "maxOpen": "",  
    "buyOpenCost": "",  
    "sellOpenCost": "",  
    "maxBuyOpen": "",  
    "maxSellOpen": ""  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| available | String | Available   For spot/margin When `side=buy`, it represents the number of quote coins; when `side=sell`, it represents the number of base coins.   The futures represents the quantity of the quote coins |
| maxOpen | String | Maximum openable size   When `side=buy`, it represents the number of quote coins; when `side=sell`, it represents the number of base coins.   Only the margin has a value. |
| buyOpenCost | String | When buying, the quantity of the quote coin required to open a position is calculated based on the input `size`.  Only the futures has a value. |
| sellOpenCost | String | When selling, the quantity of the quote coin required to open a position is calculated based on the input `size`. Only the futures has a value. |
| maxBuyOpen | String | The maximum position that can be opened for purchase.   Base coin quantity calculated based on account balance.  Only the futures has a value. |
| maxSellOpen | String | The maximum position that can be opened for sale.   Base coin quantity calculated based on account balance.   Only the futures has a value. |