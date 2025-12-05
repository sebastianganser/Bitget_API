# Equity Channel

### Description[​](#description "Direct link to Description")

Subscribe equity channel

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
            "channel": "equity"  
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

Response Example

```json
{  
  "event": "subscribe",  
  "arg": {  
    "instType": "USDT-FUTURES",  
    "channel": "equity",  
    "instId": "default"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| event | String | Yes Operation |
| arg | Object | Subscribed channels |
| > instType | String | Product type `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures |
| > channel | String | Channel name |
| msg | String | Error message |

Push Data

```json
{  
  "action": "snapshot",  
  "arg": {  
    "instType": "USDT-FUTURES",  
    "channel": "equity"  
  },  
  "data": [  
    {  
      "btcEquity": "0.0021",  
      "usdtEquity": "13.985457617660",  
      "unrealizedPL": "0.000000000000",  
      "unionTotalMargin": "100",  
      "unionAvailable": "11",  
      "unionMm": "11"  
    }  
  ],  
  "ts": 1695717225146  
}
```

### Push Parameters[​](#push-parameters "Direct link to Push Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| action | String | action, `snapshot` |
| arg | Object | Channel |
| > instType | String | Product type `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures |
| > channel | String | Channel name |
| data | List<Object> | Subscribed data |
| >usdtEquity | String | Account equity (USDT) |
| >btcEquity | String | Account equity (BTC) |
| >unrealizedPL | String | Unrealized profit and loss |
| >unionTotalMargin | String | Total multi-asset margin |
| >unionAvailable | String | Available balance under multi-asset margin mode |
| >unionMm | String | Maintenance margin under multi-asset margin mode |