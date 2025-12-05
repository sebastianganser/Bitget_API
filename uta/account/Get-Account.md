# Get Account Assets

### Description[​](#description "Direct link to Description")

Query account information and assets, with only non-zero balances being returned.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/account/assets
* Rate limit: 20/sec/UID
* Permission: UTA mgt. (read)

Request

```json
curl "https://api.bitget.com/api/v3/account/assets" \  
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
  "requestTime": 1746687063471,  
  "data": {  
    "accountEquity": "11.13919278",  
    "usdtEquity": "11.13921165",  
    "btcEquity": "0.00011256",  
    "unrealisedPnl": "0",  
    "usdtUnrealisedPnl": "0",  
    "btcUnrealizedPnl": "0",  
    "effEquity": "6.19299777",  
    "mmr": "0",  
    "imr": "0",  
    "mgnRatio": "0",  
    "positionMgnRatio": "0",  
    "assets": [  
      {  
        "coin": "USDT",  
        "equity": "6.19300826",  
        "usdValue": "6.19299777",  
        "balance": "6.19300826",  
        "available": "6.19300826",  
        "debt": "0",  
        "locked": "0"  
      },  
      {  
        "coin": "BGB",  
        "equity": "1.15582129",  
        "usdValue": "4.94618029",  
        "balance": "1.15582129",  
        "available": "1.15582129",  
        "debt": "0",  
        "locked": "0"  
      }  
    ]  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| accountEquity | String | Account equity (USD) |
| usdtEquity | String | Account equity (USDT) |
| btcEquity | String | Account equity (BTC) |
| unrealisedPnl | String | Unrealised profit and loss (USD) |
| usdtUnrealisedPnl | String | Unrealised profit and loss (USDT) |
| btcUnrealizedPnl | String | Unrealised profit and loss (BTC) |
| effEquity | String | Effective equity (USD)  The net value available for margin in spot and perpetual trades under cross-margin mode, converted to fiat |
| mmr | String | Maintenance margin (USD)  The minimum margin required to maintain the position, converted to fiat |
| imr | String | Initial margin (USD)  Total initial margin of assets in base coin, converted to fiat |
| mgnRatio | String | Margin ratio |
| positionMgnRatio | String | Position MMR |
| assets | Array | Asset list |
| >coin | String | Coin name |
| >equity | String | Coin equity |
| >usdValue | String | Coin equity (USD) |
| >balance | String | Coin balance |
| >debt | String | Debt *Applicable when placing margin orders* |
| >available | String | Available |
| >locked | String | Locked *Applicable when placing spot orders* |