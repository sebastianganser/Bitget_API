# Order Channel

### Description[​](#description "Direct link to Description")

Get order information. Initial subscriptions will not trigger any push notifications.

Data will be pushed when the following events occurred:

1. Place orders
2. Orders are filled
3. Cancel orders
4. Modify orders

Request Example

```json
{  
    "op": "subscribe",  
    "args": [  
        {  
            "instType": "SPOT",  
            "channel": "orders",  
            "instId": "BTCUSDT"  
        }  
    ]  
}
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| op | String | Yes | Operation, subscribe unsubscribe |
| args | List<Object> | Yes | List of channels to request subscription |
| > instType | String | Yes | Product line type |
| > channel | String | Yes | Channel name |
| > instId | String | Yes | Product ID, e.g. `ETHUSDT` `default`:subscribe all symbols |

Response Example

```json
{  
  "event": "subscribe",  
  "arg": {  
    "instType": "SPOT",  
    "channel": "orders",  
    "instId": "BTCUSDT"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| event | String | Yes Event |
| arg | Object | Subscribed channels |
| > instType | String | Product type |
| > channel | String | Channel name |
| > instId | String | Product ID, e.g. ETHUSDT |
| code | String | Error code, returned only on error |
| msg | String | Error message |

Push Data

```json
{  
  "action": "snapshot",  
  "arg": {  
    "instType": "SPOT",  
    "channel": "orders",  
    "instId": "BTCUSDT"  
  },  
  "data": [  
    {  
      "instId": "BTCUSDT",  
      "orderId": "1",  
      "clientOid": "1",  
      "size": "8.0000",  
      "newSize": "500.0000",  
      "notional": "8.000000",  
      "orderType": "market",  
      "force": "gtc",  
      "side": "buy",  
      "fillPrice": "26256.0",  
      "tradeId": "1",  
      "baseVolume": "0.0003",  
      "fillTime": "1695797773286",  
      "fillFee": "-0.00000018",  
      "fillFeeCoin": "BTC",  
      "tradeScope": "T",  
      "accBaseVolume": "0.0003",  
      "priceAvg": "26256.0",  
      "status": "partially_filled",  
      "cTime": "1695797773257",  
      "uTime": "1695797773326",  
      "stpMode": "cancel_taker",  
      "feeDetail": [  
        {  
          "feeCoin": "BTC",  
          "fee": "-0.00000018"  
        }  
      ],  
      "enterPointSource": "WEB"  
    }  
  ],  
  "ts": 1695797773370  
}
```

### Push Parameters[​](#push-parameters "Direct link to Push Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| arg | Object | Channels with successful subscription |
| > instType | String | Product type |
| > channel | String | Channel name |
| > instId | String | Yes |
| action | String | Push data action, `snapshot` or `update` |
| data | List<Object> | Subscription data |
| > instId | String | Product ID, e.g. ETHUSDT |
| > orderId | String | Order ID |
| > clientOid | String | Customized order ID |
| > price | String | Order price |
| > size | String | Order amount when `side=buy`, it represents the amount of quote coin; when `side=sell`, it represents the amount of base coin. |
| > newSize | String | `newSize` represents the order quantity, following the specified rules: when `orderType=limit`, `newSize` represents the quantity of base coin, when `orderType=market`and`side=buy`, `newSize` represents the quantity of quote coin, when `orderType=market`and`side=sell`, `newSize` represents the quantity of base coin. |
| > notional | String | Buy amount, returned when buying at market price |
| > ordType | String | Order type, market: market order. Limit: limit order |
| > force | String | Order validity, GTC: normal limit order, good till canceled. post\_only Post only. FOK: Fill or kill. IOC: Immediate or cancel. |
| > side | String | Order direction |
| > fillPrice | String | Latest filled price |
| > tradeId | String | Latest transaction ID |
| > baseVolume | String | Number of latest filled orders |
| > fillTime | String | Latest transaction time |
| > fillFee | String | Transaction fee of the latest transaction, negative value |
| > fillFeeCoin | String | Currency of transaction fee of the latest transaction |
| > tradeScope | String | Direction of liquidity of the latest transaction `T`:taker; `M`:maker; |
| > accBaseVolume | String | Total filled quantity |
| > priceAvg | String | Total average filled price. If the filled orders are 0, the field is 0. |
| > status | String | Order status `live`:new order; `partially_filled`:partially filled; `filled`:full filled; `cancelled`: cancelled; |
| > enterPointSource | String | Order source |
| > feeDetail | List<Object> | transaction fee list |
| >> feeCoin | String | Transaction fee currency |
| >> fee | String | Order transaction fee, the transaction fee charged by the platform from the user. |
| > cTime | String | Order creation time, milliseconds format of Unix timestamp, e.g.1630410492847 |
| > uTime | String | Order Update time, milliseconds format of Unix timestamp, e.g.1630410492847 |
| > stpMode | String | STP Mode   `none` not setting STP   `cancel_taker` cancel taker order   `cancel_maker` cancel maker order   `cancel_both` cancel both of taker and maker orders |