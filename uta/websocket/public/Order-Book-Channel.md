# Depth Channel

### Description[​](#description "Direct link to Description")

Push depth data. `books` is the full depth channel, `books1` is the 1-level channel, `books5` is the 5-level channel,
and `books50` is the 50-level channel:

* `books` corresponds to full-depth data, the first push is the full data `snapshot`, subsequent pushes are incremental
  updates: `update`
* `books1` corresponds to 1-level depth data, every push: `snapshot`
* `books5` corresponds to 5-level depth data, every push: `snapshot`
* `books50` corresponds to 50-level depth data, every push: `snapshot`

Spot

* `books1` push frequency: 60ms
* `books5` push frequency: 200ms
* `books50` push frequency: 200ms
* `books` push frequency: 200ms
* The push frequency of the order book channel (books1) is optimized to 20ms. The symbols for this optimization are: BTCUSDT, ETHUSDT, XRPUSDT, SOLUSDT, SUIUSDT, DOGEUSDT, ADAUSDT, PEPEUSDT, LINKUSDT, HBARUSDT

Futures

* `books1` push frequency: 100ms
* `books5` push frequency: 150ms
* `books50` push frequency: 150ms
* `books` push frequency: 150ms
* The push frequency of the order book channel (books1) is optimized to 20ms. The symbols for this optimization are: BTCUSDT, ETHUSDT, XRPUSDT, SOLUSDT, SUIUSDT, DOGEUSDT, ADAUSDT, PEPEUSDT, LINKUSDT, HBARUSDT

The serial number of the previous push `pseq` :

* Under normal circumstances, the serial numbers pushed by the depth channel are incremental, meaning that the `seq` value received in a push sequence is always greater than the `pseq`.
* In cases such as system releases or service restarts, the serial numbers may be reset. At this time, users will most likely receive a push message with `pseq=0`. After the reset, all subsequent messages will continue to be ordered normally.
* The seq of the previous update incremental message must be equal to the pseq of the following update incremental message.
* The seq of update incremental messages should be increasing, except during symbol maintenance.
* After receiving a snapshot (full snapshot), the seq of the snapshot should fall within the range [pseq, seq] of the first update incremental data received after the snapshot.

Request

```json
{  
    "op": "subscribe",  
    "args": [  
        {  
            "instType": "usdt-futures",  
            "topic": "books",  
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
| > topic | String | Yes | Topic   `books` All levels   `books1` 1 level   `books5` 5 levels   `books50` 50 levels |
| > symbol | String | Yes | Symbol name   e.g., `BTCUSDT` |

Response

```json
{  
  "event": "subscribe",  
  "arg": {  
    "instType": "usdt-futures",  
    "topic": "books",  
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
| > topic | String | Topic |
| code | String | Error code |
| msg | String | Error message |

Push

```json
{  
  "data": [  
    {  
      "a": [  
        [  
          "99756.7",  
          "23.9774"  
        ]  
      ],  
      "b": [  
        [  
          "99756.6",  
          "0.0128"  
        ]  
      ],  
      "checksum": 0,  
      "pseq": 0,  
      "seq": 1304314508780744705,  
      "ts": "1746698732562"  
    }  
  ],  
  "arg": {  
    "instType": "usdt-futures",  
    "symbol": "BTCUSDT",  
    "topic": "books1"  
  },  
  "action": "snapshot",  
  "ts": 1746698732563  
}
```

### Push Parameters[​](#push-parameters "Direct link to Push Parameters")

| Return Field | Parameter Type | Description |
| --- | --- | --- |
| arg | Object | Subscribed channel |
| > instType | String | Product type `spot` Spot trading `usdt-futures` USDT futures   `coin-futures` Coin-M futures   `usdc-futures` USDC futures |
| > topic | String | Topic |
| action | String | Data push action   `snapshot` Full push   `update` Incremental push |
| ts | String | Data push action   `snapshot` Full push   `update` Incremental push |
| data | List<String> | Subscribed data |
| > a | List<String> | Sell Asks. Sort by price in ascending order |
| > > a[0] | String | Sell price |
| > > a[1] | String | Sell quantity |
| > b | List<String> | Buy bids. Sort by price in descending order |
| > > b[0] | String | Buy Price |
| > > b[1] | String | Buy quantity |
| > > checksum | String | Checksum It is used to verify the accuracy of the data. |
| > > seq | String | Serial number.  It increments when the order book is updated and can be used to determine whether there is out-of-order packets. |
| > > pseq | String | The serial number of the previous push.   Can be used to determine if there has been packet loss. This field only has a value for the books channel. |
| > > ts | String | The timestamp that the system generated data  A Unix timestamp in milliseconds |