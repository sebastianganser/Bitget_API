# Account

### Description[​](#description "Direct link to Description")

Data will be pushed when the following events occurred:

1. Push on first-time subscription
2. Push when spot/margin/futures orders are filled in the unified trading account
3. Push when the fund settlement is done
4. Push when balance changes (transfers, airdrops, loans, etc.)

Request Example

```json
{  
    "op": "subscribe",  
    "args": [  
        {  
            "instType": "UTA",  
            "topic": "account"  
        }  
    ]  
}
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| op | String | Yes | Operation   `subscribe`/`unsubscribe` |
| args | List<Object> | Yes | Subscribed channels |
| > instType | String | Yes | Product Type   `UTA` Unified trading account |
| > topic | String | Yes | Topic `account` |

Response

```json
{  
    "event": "subscribe",  
    "arg": {  
        "instType": "UTA",  
        "topic": "account"  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| event | String | Operation   `subscribe` Subscribe   `unsubscribe` Unsubscribe   `error` Parameter Error |
| arg | Object | Subscribed Channel |
| > instType | String | Product Type   `UTA` |
| > topic | String | Topic   `account` |
| code | String | Error Code |
| msg | String | Error Message |

Push Data

```json
{  
  "data": [{  
    "unrealisedPnL": "-10116.55",  
    "totalEquity": "4976919.05",  
    "positionMgnRatio": "0",  
    "mmr": "408.08",  
    "effEquity": "4847952.35",  
    "imr": "17795.97",  
    "mgnRatio": "0",  
    "coin": [{  
      "debts": "0",  
      "balance": "0.9992",  
      "available": "0.9992",  
      "borrow": "0",  
      "locked": "0",  
      "equity": "0.9992",  
      "coin": "ETH",  
      "usdValue": "2488.667472"  
    }, {  
      "debts": "0",  
      "balance": "52.00819",  
      "available": "52.00819",  
      "borrow": "0",  
      "locked": "0",  
      "equity": "52.00819",  
      "coin": "BTC",  
      "usdValue": "4630564.31304974"  
    }, {  
      "debts": "0",  
      "balance": "354411.45536458",  
      "available": "344282.65536458",  
      "borrow": "0",  
      "locked": "0",  
      "equity": "344282.65536458",  
      "coin": "USDT",  
      "usdValue": "343866.07335159"  
    }]  
  }],  
  "arg": {  
    "instType": "UTA",  
    "topic": "account"  
  },  
  "action": "snapshot",  
  "ts": 1740546523244  
}
```

### Push Parameters[​](#push-parameters "Direct link to Push Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| action | String | Action `snapshot` |
| ts | String | Timestamp |
| arg | Object | Subscribe channel |
| > instType | String | Product type  `UTA` |
| > topic | String | Topic `account` |
| data | List | Subscribed data |
| > totalEquity | String | Account equity (USD) |
| > effEquity | String | Effective margin (USD)  The net value available for margin in spot and perpetual trades under cross-margin mode, converted to fiat |
| > mmr | String | Maintenance margin (USD)  The minimum margin required to maintain the position, converted to fiat |
| > imr | String | Initial margin (USD) Total initial margin of assets in base coin, converted to fiat |
| > mgnRatio | String | Margin ratio |
| >positionMgnRatio | String | Hold position margin ratio |
| > unrealisedPnl | String | Unrealised profit and loss |
| > coin | List | Coin list |
| >> coin | String | Coin name |
| >> balance | String | Coin balance |
| >> locked | String | Locked amount   *Only applicable for spot order placement* |
| >> equity | String | Coin equity (USD) |
| >> usdValue | String | Coin value (USD) |
| >> available | String | Available balance |
| >> borrow | String | Borrowed amount |
| >> debts | String | Debt   *Only applicable for margin trading* |