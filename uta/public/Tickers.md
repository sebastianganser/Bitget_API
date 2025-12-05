# Get Tickers

### Description[​](#description "Direct link to Description")

Query real-time market data, including the latest price, 24-hour high/low, volume, bid, ask, and price change for available trading pairs.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/market/tickers
* Rate limit: 20/sec/IP

Request

```json
curl "https://api.bitget.com/api/v3/market/tickers?category=SPOT&symbol=BTCUSDT"  \
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameters | Type | Required | Description |
| --- | --- | --- | --- |
| category | String | Yes | Product type   `SPOT` Spot trading   `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures |
| symbol | String | No | Symbol name  e.g.,`BTCUSDT` |

* Spot
* Futures

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1735109995767,  
  "data": [  
    {  
      "category": "SPOT",  
      "symbol": "BTCUSDT",  
      "lastPrice": "4038",  
      "openPrice24h": "0",  
      "highPrice24h": "0",  
      "lowPrice24h": "0",  
      "ask1Price": "",  
      "bid1Price": "4038",  
      "bid1Size": "0.390495",  
      "ask1Size": "0",  
      "price24hPcnt": "0",  
      "volume24h": "0",  
      "turnover24h": "0",  
    }  
  ]  
}
```

Response

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1735110108752,  
    "data": [  
        {  
            "category": "USDT-FUTURES",  
            "symbol": "BTCUSDT",  
            "lastPrice": "97999.9",  
            "openPrice24h": "97996.6",  
            "highPrice24h": "98003.4",  
            "lowPrice24h": "97996.6",  
            "ask1Price": "98000.1",  
            "bid1Price": "97999.9",  
            "bid1Size": "9.69",  
            "ask1Size": "9.69",  
            "price24hPcnt": "0.00003",  
            "volume24h": "52.0516",  
            "turnover24h": "5101050.26784",  
            "indexPrice": "120000",  
            "markPrice": "98000",  
            "fundingRate": "0.000001",  
            "openInterest": "1411.1397",  
            "deliveryStartTime": "",  
            "deliveryTime": "",  
            "deliveryStatus": ""  
        }  
    ]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameters | Type | Description |
| --- | --- | --- |
| symbol | String | Symbol name  e.g.,`BTCUSDT` |
| category | String | Product type   `SPOT` Spot trading   `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures |
| lastPrice | String | Latest price |
| openPrice24h | String | Market price 24 hours ago |
| lowPrice24h | String | Lowest price in the last 24 hours |
| highPrice24h | String | Highest price in the last 24 hours |
| ask1Price | String | Best ask price |
| bid1Price | String | Best bid price |
| bid1Size | String | Best bid quantity |
| ask1Size | String | Best ask quantity |
| price24hPcnt | String | 24-hour price change percentage |
| turnover24h | String | 24-hour turnover |
| volume24h | String | 24-hour volume |
| indexPrice | String | Index price   Available only for futures |
| markPrice | String | Mark price   Available only for futures |
| fundingRate | String | Funding rate   Available only for futures |
| openInterest | String | Open interest   Available only for futures |
| deliveryStartTime | String | Delivery start time   Available only for deliveries |
| deliveryTime | String | Delivery time   Available only for deliveries |
| deliveryStatus | String | Delivery status   `delivery_config_period` New pair configuration   `delivery_normal` Trading   `delivery_before` 10 minutes before delivery, no new orders   `delivery_period` During delivery, no opening or closing of positions, and no order cancellation   Available only for deliveries |
| ts | String | The timestamp that the system generated the data  A Unix timestamp in milliseconds |