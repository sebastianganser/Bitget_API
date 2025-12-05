# Tickers Channel

### Description[​](#description "Direct link to Description")

Get the latest transaction price, best bid, best ask, and 24-hour trading volume for the product. When there are
changes (transactions, best bid/ask updates), the push frequency is:

* Spot push frequency: 200-300ms
* Futures push frequency: 300-400ms

Request

```json
{  
    "op": "subscribe",  
    "args": [  
        {  
            "instType": "spot",  
            "topic": "ticker",  
            "symbol": "BTCUSDT"  
        }  
    ]  
}
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameters | Type | Required | Description |
| --- | --- | --- | --- |
| op | String | Yes | Operation   `subscribe` Subscribe   `unsubscribe` Unsubscribe |
| args | List<Object> | Yes | Subscribed channel |
| > instType | String | Yes | Product type `spot` Spot trading `usdt-futures` USDT futures   `coin-futures` Coin-M futures   `usdc-futures` USDC futures |
| > topic | String | Yes | Topic   `ticker` Market data channel |
| > symbol | String | Yes | Trading pair   e.g. `BTCUSDT` |

Response

```json
{  
  "event": "subscribe",  
  "arg": {  
    "instType": "spot",  
    "topic": "ticker",  
    "symbol": "BTCUSDT"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameters | Type | Description |
| --- | --- | --- |
| event | String | Event |
| arg | Object | Subscribed channel |
| > instType | String | Product type `spot` Spot trading `usdt-futures` USDT futures   `coin-futures` Coin-M futures   `usdc-futures` USDC futures |
| > topic | String | Topic   `ticker` Ticker channel |
| code | String | Error code |
| msg | String | Error message |

Push

```json
{  
  "data": [  
    {  
      "bid1Price": "99999",  
      "lowPrice24h": "98200",  
      "ask1Size": "188.312553",  
      "volume24h": "37.722858",  
      "price24hPcnt": "0.01833",  
      "highPrice24h": "100000",  
      "turnover24h": "3750302.979626",  
      "bid1Size": "186.183209",  
      "ask1Price": "100000",  
      "openPrice24h": "0",  
      "lastPrice": "100000"  
    }  
  ],  
  "arg": {  
    "instType": "spot",  
    "symbol": "BTCUSDT",  
    "topic": "ticker"  
  },  
  "action": "snapshot",  
  "ts": 1736371332162  
}
```

### Push Parameters[​](#push-parameters "Direct link to Push Parameters")

#### Spot Push[​](#spot-push "Direct link to Spot Push")

| Parameters | Parameter Type | Description |
| --- | --- | --- |
| arg | Object | Subscribed channel |
| > instType | String | Product type  `spot` Spot trading |
| > topic | String | Topic   `ticker` Ticker channel |
| > symbol | String | Symbol name |
| action | String | Data push action   `snapshot` Full data   `update` Incremental data |
| data | List<String> | Subscribed data |
| > highPrice24h | String | Highest price in the last 24 hours |
| > lowPrice24h | String | Lowest price in the last 24 hours |
| > openPrice24h | String | Market price 24 hours ago |
| > lastPrice | String | Latest price |
| > turnover24h | String | 24-hour turnover |
| > volume24h | String | 24-hour volume |
| > bid1Price | String | Best bid price |
| > ask1Price | String | Best ask price |
| > bid1Size | String | Best bid quantity |
| > ask1Size | String | Best ask quantity |
| > price24hPcnt | String | 24-hour price change percentage |

#### Futures Push[​](#futures-push "Direct link to Futures Push")

| Parameters | Parameter Type | Description |
| --- | --- | --- |
| arg | Object | Subscribed successful channel |
| > instType | String | Product type `usdt-futures` USDT futures   `coin-futures` Coin-M futures   `usdc-futures` USDC futures |
| > topic | String | Topic   `ticker` Ticker channel |
| action | String | Data push action   `snapshot` Full data   `update` Incremental data |
| data | List<String> | Subscribed data |
| > highPrice24h | String | Highest price in the last 24 hours |
| > lowPrice24h | String | Lowest price in the last 24 hours |
| > openPrice24h | String | Market price 24 hours ago |
| > lastPrice | String | Latest price |
| > turnover24h | String | 24-hour turnover |
| > volume24h | String | 24-hour volume |
| > bid1Price | String | Best bid price |
| > ask1Price | String | Best ask price |
| > bid1Size | String | Best bid quantity |
| > ask1Size | String | Best ask quantity |
| > price24hPcnt | String | 24-hour price change percentage |
| > indexPrice | String | Index price   Available only for futures |
| > markPrice | String | Mark price   Available only for futures |
| > fundingRate | String | Funding rate   Available only for futures |
| > nextFundingTime | String | Next funding rate settlement time |
| > openInterest | String | Open interest   Available only for futures |
| > deliveryTime | String | Delivery time   Available only for deliveries |
| > deliveryStartTime | String | Delivery start time   Available only for deliveries |
| > deliveryStatus | String | Delivery status   `delivery_config_period` New pair configuration   `delivery_normal` Trading   `delivery_before` 10 minutes before delivery, no new orders   `delivery_period` During delivery, no opening or closing of positions, and no order cancellation   Available only for deliveries |