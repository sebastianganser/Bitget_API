# Liquidation Channel

### Description[​](#description "Direct link to Description")

Liquidation Channel

Request

```json
{  
    "args": [  
        {  
            "instType": "usdt-futures",  
            "topic": "liquidation"  
        }  
    ],  
    "op": "subscribe"  
}
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameters | Type | Required | Description |
| --- | --- | --- | --- |
| op | String | Yes | Operation   `subscribe` Subscribe   `unsubscribe` Unsubscribe |
| args | List<Object> | Yes | Subscribed channel |
| > instType | String | Yes | Product type `usdt-futures` USDT futures   `coin-futures` Coin-M futures   `usdc-futures` USDC futures |
| > topic | String | Yes | Topic   `liquidation` Liquidation channel |

Response

```json
{  
  "event": "subscribe",  
  "arg": {  
    "instType": "usdt-futures",  
    "topic": "liquidation"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameters | Type | Description |
| --- | --- | --- |
| event | String | Event |
| arg | Object | Subscribed channel |
| > instType | String | Product type `usdt-futures` USDT futures   `coin-futures` Coin-M futures   `usdc-futures` USDC futures |
| > topic | String | Topic   `liquidation` Liquidation channel |
| code | String | Error code |
| msg | String | Error message |

Push

```json
{  
  "data": [  
    {  
      "symbol": "BTCUSDT",  
      "side": "buy",  
      "price": "89000",  
      "amount": "37.722858",  
      "ts": "1736371332162"  
    }  
  ],  
  "arg": {  
    "instType": "usdt-futures",  
    "topic": "liquidation"  
  },  
  "action": "update",  
  "ts": 1736371332162  
}
```

### Push Parameters[​](#push-parameters "Direct link to Push Parameters")

| Parameters | Parameter Type | Description |
| --- | --- | --- |
| arg | Object | Subscribed successful channel |
| > instType | String | Product type `usdt-futures` USDT futures   `coin-futures` Coin-M futures   `usdc-futures` USDC futures |
| > topic | String | Topic   `liquidation` Liquidation channel |
| action | String | Data push action   `snapshot` Full data   `update` Incremental data |
| data | List<String> | Subscribed data |
| >symbol | String | Symbol name |
| >side | String | Position side `buy`Long position liquidation `sell`Short position liquidation |
| >price | String | Liquidation price |
| >amount | String | Liquidation amount |
| >ts | String | Liquidation time (Unix millisecond timestamp) |