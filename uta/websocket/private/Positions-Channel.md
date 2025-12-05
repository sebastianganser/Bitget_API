# Position

### Description[​](#description "Direct link to Description")

Data will be pushed when the following events occur:

1. Push on the first-time subscription
2. Push incremental data when close-position orders are placed in the unified trading account
3. Push incremental data when futures positions are opened in the unified trading account
4. Push incremental data when futures positions are closed in the unified trading account
5. Push incremental data when futures close-position orders are modified in the unified trading account
6. Push incremental data when futures close-position orders are cancelled in the unified trading account

Request

```json
{  
    "op": "subscribe",  
    "args": [  
        {  
            "instType": "UTA",  
            "topic": "position"  
        }  
    ]  
}
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameters | Type | Description |
| --- | --- | --- |
| op | String | Operation   `subscribe` Subscribe  `unsubscribe` Unsubscribe |
| args | List<Object> | Subscribed channel |
| > instType | String | Product type  `UTA` Unified trading account |
| > topic | String | Topic `position` Position |

Response

```json
{  
  "event": "subscribe",  
  "arg": {  
    "instType": "UTA",  
    "topic": "position"  
  },  
  "code": "",  
  "msg": ""  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameters | Type | Description |
| --- | --- | --- |
| event | String | Operation  `subscribe` Subscription  `unsubscribe` Unsubscription  `error` Parameter error |
| arg | Object | Subscribed channel |
| > instType | String | Product type  `UTA` Unified trading account |
| > topic | String | Topic  `position` Position |
| code | String | Error code |
| msg | String | Error message |

Push

```json
{  
  "data": [  
    {  
      "symbol": "BTCUSDT",  
      "leverage": "20",  
      "openFeeTotal": "",  
      "mmr": "",  
      "breakEvenPrice": "",  
      "available": "0",  
      "liqPrice": "",  
      "marginMode": "crossed",  
      "unrealisedPnl": "0",  
      "markPrice": "94987.1",  
      "createdTime": "1736378720620",  
      "avgPrice": "0",  
      "totalFundingFee": "0",  
      "updatedTime": "1736378720620",  
      "marginCoin": "USDT",  
      "frozen": "0",  
      "profitRate": "",  
      "closeFeeTotal": "",  
      "marginSize": "0",  
      "curRealisedPnl": "0",  
      "size": "0",  
      "positionStatus": "ended",  
      "posSide": "long",  
      "holdMode": "hedge_mode"  
    }  
  ],  
  "arg": {  
    "instType": "UTA",  
    "topic": "position"  
  },  
  "action": "snapshot",  
  "ts": 1730711666652  
}
```

### Push Parameters[​](#push-parameters "Direct link to Push Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| arg | Object | Subscribed channel |
| > instType | String | Product type  `UTA` Unified Account |
| > topic | String | Topic  `position` Position channel |
| action | String | Action  `snapshot` Full data  `update` Incremental data |
| data | List<String> | Subscribed data |
| > symbol | String | Symbol name |
| > marginCoin | String | Margin coin |
| > marginSize | String | Margin size |
| > marginMode | String | Margin mode |
| > posSide | String | Position side  `long`/`short` |
| > holdMode | String | Holding mode   `one_way_mode`/`hedge_mode` |
| > positionStatus | String | Position status   `opening` Ongoing   `ended` Completed |
| > size | String | Position size  `size` = `available` + `frozen` |
| > available | String | Available position size |
| > frozen | String | Frozen position size |
| > avgPrice | String | Average open price |
| > leverage | String | Leverage multiple |
| > curRealisedPnl | String | Realised PnL |
| > unrealisedPnl | String | Unrealised PnL |
| > liqPrice | String | Estimated liquidation price |
| > mmr | String | Maintain margin rate |
| > marginRate | String | Margin rate |
| > breakEvenPrice | String | Break-even price |
| > profitRate | String | Profit rate *Profit rate = Unrealized PnL ÷ Initial margin* *Initial margin = Average open price × Position size ÷ Leverage ÷ Margin coin index price* |
| > totalFundingFee | String | Total funding fee over the position's lifetime  `0` indicates that no funding fee has been charged yet |
| > createdTime | String | Created time A Unix timestamp in milliseconds. e.g.,`1597026383085` |
| > updatedTime | String | Updated time A Unix timestamp in milliseconds. e.g.,`1597026383085` |