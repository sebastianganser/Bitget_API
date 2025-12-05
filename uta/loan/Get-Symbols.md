# Get Trade Symbols

### Description[​](#description "Direct link to Description")

Get Trade Symbols

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/ins-loan/symbols
* Rate limit: 3/sec/UID
* Permission: UTA mgt. (read)

Request

```json
curl "https://api.bitget.com/api/v3/ins-loan/symbols?productId=xxxxxxxx" \  
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
| productId | String | Yes | Product Id |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1711697588556,  
  "data": {  
    "productId": "xxxxxxxx",  
    "spotSymbols": [  
      "USDCUSDT",  
      "BTCUSDT",  
      "ETHUSDT",  
      "BGBUSDT"  
    ],  
    "usdtContractLeverage": "3",  
    "coinContractLeverage": "3",  
    "usdcContractLeverage": "3",  
    "usdtContractSymbols": [  
      {  
        "symbol": "BTCUSDT",  
        "leverage": "15"  
      },  
      {  
        "symbol": "ETHUSDT",  
        "leverage": "5"  
      }  
    ],  
    "coinContractSymbols": [],  
    "usdcContractSymbols": [  
      {  
        "symbol": "BTCUSD",  
        "leverage": "5"  
      }  
    ]  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| productId | String | Product Id |
| spotSymbols | Array | Spot trading pairs |
| usdtContractLeverage | String | The allowed default leverage for USDT-M Futures |
| coinContractLeverage | String | The allowed default leverage for Coin-M Futures |
| usdcContractLeverage | String | The allowed default leverage for USDC-M Futures |
| usdtContractSymbols | Array | USDT-M Futures Object  If `supportUsdtContract`= `NO`, then it returns "[]"  If there are whitelist symbols, it return those whitelist data |
| > symbol | String | Symbol name |
| > leverage | String | Maximum leverage |
| coinContractSymbols | Array | Coin-M Futures Object   If `supportCoinContract`= `NO`, then it returns "[]"  If there are whitelist symbols, it return those whitelist data |
| > symbol | String | Symbol name |
| > leverage | Array | Maximum leverage |
| usdcContractSymbols | Array | USDC-M Futures Object   If `supportUsdcContract`= `NO`, then it returns "[]"  If there are whitelist symbols, it return those whitelist data |
| > symbol | String | Symbol name |
| > leverage | String | Maximum leverage |