# Get Position Info

### Description[​](#description "Direct link to Description")

Query real-time position data by symbol, side, or category.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/position/current-position
* Rate limit: 20/sec/UID
* Permission: UTA trade (read)

Request

```json
curl "https://api.bitget.com/api/v3/position/current-position?category=USDT-FUTURES&symbol=EOSUSDT" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*" \  
  -H "ACCESS-PASSPHRASE:*" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:zh-CN" \  
  -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| category | String | Yes | Product type   `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures |
| symbol | String | No | Symbol name e.g.`BTCUSDT` If no symbol is provided, all positions in the corresponding category will be returned. |
| posSide | String | No | Position side  `long`/`short`  If this field is provided, only the position in the corresponding side will be returned. |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1753103840140,  
  "data": {  
    "list": [  
      {  
        "category": "USDT-FUTURES",  
        "symbol": "BTCUSDT",  
        "marginCoin": "USDT",  
        "holdMode": "hedge_mode",  
        "posSide": "long",  
        "marginMode": "crossed",  
        "positionBalance": "4701531.84941582",  
        "available": "119.2068",  
        "frozen": "0",  
        "total": "119.2068",  
        "leverage": "3",  
        "curRealisedPnl": "0",  
        "avgPrice": "108674",  
        "positionStatus": "normal",  
        "unrealisedPnl": "1124573.04243999",  
        "liquidationPrice": "43099.9",  
        "mmr": "0.015",  
        "profitRate": "0.2391929010498401",  
        "markPrice": "118097",  
        "breakEvenPrice": "109208.6",  
        "totalFunding": "-53076.32433032",  
        "openFeeTotal": "-2842.86603479",  
        "closeFeeTotal": "0",  
        "createdTime": "1736378720620",  
        "updatedTime": "1753102803148"  
      }  
    ]  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| list | Array | Position list |
| >category | String | Product Type  `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures |
| >symbol | String | Symbol name |
| >marginCoin | String | Margin coin |
| >posSide | String | Position side  `long`/`short` |
| >positionBalance | String | Position balance *The unit is margin coin* |
| >available | String | Available position |
| >frozen | String | Frozen position |
| >total | String | Total position (available + frozen) |
| >leverage | String | Leverage multiple |
| >curRealisedPnl | String | Current realised profit and loss |
| >avgPrice | String | Average entry price |
| >marginMode | String | Margin mode `crossed` crossed margin `isolated` isolated margin |
| >positionStatus | String | Position status `normal` |
| >holdMode | String | Holding mode `one_way_mode`/`hedge_mode` |
| >unrealisedPnl | String | Unrealised profit and loss |
| >liquidationPrice | String | Estimated liquidation price Less than or equal to 0 means liquidation will not occur |
| >mmr | String | Maintenance margin rate |
| >profitRate | String | Profit rate |
| >markPrice | String | Mark price |
| >breakEvenPrice | String | Break-even price |
| >totalFunding | String | Total funding The accumulated fund fee during the position's duration. If the value is zero, it indicates no fees have been charged |
| >openFeeTotal | String | Fees deducted on position opening  Opening fees deducted during the position's lifetime |
| >closeFeeTotal | String | Fees deducted on position closing  Closing fees deducted during the position's lifetime |
| >createdTime | String | Created timestamp  A Unix millisecond timestamp |
| >updatedTime | String | Updated timestamp  A Unix millisecond timestamp |