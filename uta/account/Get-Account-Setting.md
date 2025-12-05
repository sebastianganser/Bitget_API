# Get Account Info

### Description[​](#description "Direct link to Description")

Query account information, including the holding mode, margin mode, leverage multiple, and more.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/account/settings
* Rate limit: 20/sec/UID
* Permission: UTA mgt. (read)

Request

```json
curl "https://api.bitget.com/api/v3/account/settings" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

N/A

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1753787749280,  
  "data": {  
    "uid": "1111111111",  
    "accountMode": "hybrid",  
    "assetMode": "multi_assets",  
    "holdMode": "one_way_mode",  
    "stpMode": "none",  
    "symbolConfigList": [  
      {  
        "category": "USDT-FUTURES",  
        "symbol": "BGBUSDT",  
        "marginMode": "crossed",  
        "leverage": "20"  
      },  
      {  
        "category": "USDT-FUTURES",  
        "symbol": "BMTUSDT",  
        "marginMode": "crossed",  
        "leverage": "20"  
      },  
      {  
        "category": "USDT-FUTURES",  
        "symbol": "1000SATSUSDT",  
        "marginMode": "crossed",  
        "leverage": "20"  
      },  
      {  
        "category": "USDT-FUTURES",  
        "symbol": "FUNUSDT",  
        "marginMode": "crossed",  
        "leverage": "20"  
      },  
      {  
        "category": "USDT-FUTURES",  
        "symbol": "1000BONKUSDT",  
        "marginMode": "crossed",  
        "leverage": "20"  
      },  
      {  
        "category": "USDT-FUTURES",  
        "symbol": "BTCUSDT",  
        "marginMode": "crossed",  
        "leverage": "1"  
      },  
      {  
        "category": "USDT-FUTURES",  
        "symbol": "IOTAUSDT",  
        "marginMode": "crossed",  
        "leverage": "20"  
      },  
      {  
        "category": "USDT-FUTURES",  
        "symbol": "C98USDT",  
        "marginMode": "crossed",  
        "leverage": "20"  
      }  
    ],  
    "coinConfigList": [  
      {  
        "coin": "USDT",  
        "leverage": "6"  
      },  
      {  
        "coin": "SHIB",  
        "leverage": "2"  
      },  
      {  
        "coin": "BTC",  
        "leverage": "3"  
      }  
    ]  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| uid | String | UID |
| accountMode | String | Account Mode  `unified` Unified Mode   `hybrid` Hybrid Mode  `upgrading` Unified Account Upgrading   `switching` Classic Account Switching |
| assetMode | String | Asset mode `multi_assets` Multi\_assets mode |
| holdMode | String | Holding mode `one_way_mode`/`hedge_mode` |
| stpMode | String | STP Mode   `none` not setting STP   `cancel_taker` cancel taker order   `cancel_maker` cancel maker order   `cancel_both` cancel both of taker and maker orders |
| symbolConfigList | Array | Symbol configuration list |
| >category | String | Product type  `USDT-FUTURES` USDT futures `COIN-FUTURES` Coin-M futures `USDC-FUTURES` USDC futures |
| >symbol | String | Symbol name |
| >marginMode | String | Margin mode  `crossed`/`isolated` |
| >leverage | Array | Leverage multiple |
| coinConfigList | Array | Coin configuration list |
| >coin | String | Coin name |
| >leverage | String | Leverage multiple |