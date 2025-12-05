# Get Position Tier

### Description[​](#description "Direct link to Description")

Query the position tier info.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/market/position-tier
* Rate limit: 20/sec/IP

Request

```json
curl "https://api.bitget.com/api/v3/market/position-tier?category=USDT-FUTURES&coin=ETH"  \
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| category | String | Yes | Product type `MARGIN` Margin trading   `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures |
| symbol | String | No | Symbol name  e.g.,`BTCUSDT`, applies to `Futures` |
| coin | String | No | Coin name  e.g.,`BTC`, applies to `Margin` |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1731146663643,  
  "data": [  
    {  
      "tier": "1",  
      "minTierValue": "0",  
      "maxTierValue": "100000",  
      "leverage": "125",  
      "mmr": "0.004"  
    }  
  ]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| tier | String | Position tier |
| leverage | String | Leverage |
| minTierValue | String | Minimum value of current tier  Available only for futures |
| maxTierValue | String | Maximum value of current tier  Available only for futures |
| mmr | String | Maintenance margin ratio  When the margin rate of the position falls below the maintenance margin rate, forced liquidation or position reduction will be triggered |