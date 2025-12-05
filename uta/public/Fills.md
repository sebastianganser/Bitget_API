# Get Recent Public Fills

### Description[​](#description "Direct link to Description")

Query recent public fill data on Bitget.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/market/fills
* Rate limit: 20/sec/IP

Request

```json
curl "https://api.bitget.com/api/v3/market/fills?category=USDT-FUTURES&symbol=BTCUSDT&limit=100"  \
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| category | String | Yes | Product Type  `SPOT` Spot trading   `MARGIN` Margin trading   `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures |
| symbol | String | Yes | Symbol name  e.g.,`BTCUSDT` |
| limit | String | No | Limit per page  Default: `100`. Maximum: `100` |

Response

```json
{  
  "code": "00000",  
  "data": [  
    {  
      "execId": "1",  
      "execLinkId": "12345877111",  
      "price": "29990.5",  
      "size": "0.0166",  
      "side": "sell",  
      "ts": "1627116776464"  
    },  
    {  
      "execId": "2",  
      "execLinkId": "12345877112",  
      "price": "30007.0",  
      "size": "0.0166",  
      "side": "buy",  
      "ts": "1627116600875"  
    }  
  ],  
  "msg": "success",  
  "requestTime": 1690313813709  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| >execId | String | Fill execution ID |
| >execLinkId | String | Execution correlation ID |
| >price | String | Fill price |
| >size | String | Fill size |
| >side | String | Trade side   `sell`/`buy` |
| >ts | String | Fill timestamp   A Unix timestamp in milliseconds |