# Account channel

### Description[​](#description "Direct link to Description")

Subscribe account channel

Data will be pushed when the following events occurred:

1. Transfer balance to Futures account
2. Trading voucher deposit
3. Open/close orders are filled

Request Example

```json
{  
    "op": "subscribe",  
    "args": [  
        {  
            "instType": "USDT-FUTURES",  
            "channel": "account",  
            "coin": "default"  
        }  
    ]  
}
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| op | String | Yes | Operation, subscribe unsubscribe |
| args | List<Object> | Yes | List of channels to request subscription |
| > instType | String | Yes | Product type `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures |
| > channel | String | Yes | Channel name |
| > coin | String | Yes | Coin name，`default` represents all the coins，Only default is supported now |

Response Example

```json
{  
  "event": "subscribe",  
  "arg": {  
    "instType": "USDT-FUTURES",  
    "channel": "account",  
    "coin": "default"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| event | String | Yes Operation |
| arg | Object | Subscribed channels |
| > instType | String | Product type `USDT-FUTURES` USDT professional futures `COIN-FUTURES` Futures settled in cryptocurrencies `USDC-FUTURES` USDC professional futures |
| > channel | String | Channel name |
| > coin | String | `default` |
| code | String | Error code |
| msg | String | Error message |

Push Data

```json
{  
  "action": "snapshot",  
  "arg": {  
    "instType": "USDT-FUTURES",  
    "channel": "account",  
    "coin": "default"  
  },  
  "data": [  
    {  
      "marginCoin": "USDT",  
      "frozen": "0.00000000",  
      "available": "11.98545761",  
      "maxOpenPosAvailable": "11.98545761",  
      "maxTransferOut": "11.98545761",  
      "equity": "11.98545761",  
      "usdtEquity": "11.985457617660",  
      "crossedRiskRate": "0",  
      "unrealizedPL": "0.000000000000",  
      "unionTotalMargin": "100",  
      "unionAvailable": "20",  
      "unionMm": "15",  
      "assetsMode": "union"  
    }  
  ],  
  "ts": 1695717225146  
}
```

### Push Parameters[​](#push-parameters "Direct link to Push Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| action | String | `snapshot` |
| arg | Object | Channels to request subscription |
| > instType | String | Product type `USDT-FUTURES` USDT professional futures `COIN-FUTURES` Futures settled in cryptocurrencies `USDC-FUTURES` USDC professional futures |
| > channel | String | Channel name |
| > coin | String | `default` |
| data | List<Object> | Subscription data |
| >marginCoin | String | Margin coin |
| >frozen | String | Locked quantity (margin coin) |
| >available | String | Currently available assets |
| >maxOpenPosAvailable | String | Maximum available balance to open positions |
| >maxTransferOut | String | Maximum transferable amount |
| >equity | String | Account assets |
| >usdtEquity | String | Account equity in USD |
| >crossedRiskRate | String | Risk ratio in cross margin mode |
| >unrealizedPL | String | Unrealized PnL |
| >unionTotalMargin | String | Margin Amount under Union Margin Mode |
| >unionAvailable | String | Available Balance under Union Margin Mode |
| >unionMm | String | Maintenance Margin under Union Margin Mode |
| >assetsMode | String | Account Mode `union`Unified Margin `single`Single-Currency Margin |