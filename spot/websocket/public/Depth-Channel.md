# Depth Channel

### Description[​](#description "Direct link to Description")

This is the channel to get the depth data  
Default data push frequency for `books`, `books5`, `books15` is **200ms**  
Default data push frequency for `books1` is **60ms**

* `books`: All levels of depth. First update pushed is full data: `snapshot`, and then push the update data: `update`
* `books1`: 1st level of depth. Push `snapshot` each time
* `books5`: 5 depth levels. Push `snapshot` each time
* `books15`: 15 depth levels. Push `snapshot` each time
* The push frequency of the order book channel (books1) is optimized to 20ms. The symbols for this optimization are: BTCUSDT, ETHUSDT, XRPUSDT, SOLUSDT, SUIUSDT, DOGEUSDT, ADAUSDT, PEPEUSDT, LINKUSDT, HBARUSDT

#### Checksum[​](#checksum "Direct link to Checksum")

Calculate Checksum

```json
1. More than 25 levels of bid and ask  
A local snapshot of market depth (only 2 levels of the orderbook are shown here, while 25 levels of orderbook should actually be intercepted):  
    "bids": [  
      [ 43231.1, 4 ],   //bid1  
      [ 43231,   6 ]    //bid2  
    ]  
    "asks": [  
      [ 43232.8, 9 ],   //ask1  
      [ 43232.9, 8 ]    //ask2  
    ]  
Build the string to check CRC32:  
"43231.1:4:43232.8:9:43231:6:43232.9:8"  
The sequence:  
"bid1[price:amount]:ask1[price:amount]:bid2[price:amount]:ask2[price:amount]"  
  
2. Less than 25 levels of bid or ask  
A local snapshot of market depth:  
    "bids": [  
      [ 3366.1, 7 ] //bid1  
    ]  
    "asks": [  
      [ 3366.8, 9 ],    //ask1  
      [ 3368  , 8 ],    //ask2  
      [ 3372  , 8 ]     //ask3  
    ]  
  
Build the string to check CRC32:  
"3366.1:7:3366.8:9:3368:8:3372:8"  
The sequence:  
"bid1[price:amount]:ask1[price:amount]:ask2[price:amount]:ask3[price:amount]"
```

This mechanism can assist users in checking the accuracy of depth(order book) data.

**Merging update data into snapshot**

After subscribe to the channel (such as `books` 400 levels) of [Order book](#order-book-channel) , user first receive the initial snapshot of market depth. Afterwards the incremental update is subsequently received, user are responsible to update the snapshot from client side.

1. If there are any levels with same price from the updates, compare the amount with the snapshot order book:

   If the amount is 0, delete this depth data.

   If the amount changes, replace the depth data.
2. If there is no level in the snapshot with same price from the update, insert the update depth information into the snapshot sort by price (bid in descending order, ask in ascending order).

**Calculate Checksum**

Use the first 25 bids and asks in the local snapshot to build a string (where a colon connects the price and amount in an ask or a bid), and then calculate the CRC32 value (32-bit signed integer).

1. When the bid and ask depth data exceeds 25 levels, each of them will intercept 25 levels of data, and the string to be checked is queued in a way that the bid and ask depth data are alternately arranged.
   Such as: `bid1[price:amount]`:`ask1[price:amount]`:`bid2[price:amount]`:`ask2[price:amount]`...
2. When the bid or ask depth data is less than 25 levels, the missing depth data will be ignored.
   Such as: `bid1[price:amount]`:`ask1[price:amount]`:`ask2[price:amount]`:`ask3[price:amount]`...
3. If price is '0.5000', DO NOT calculate the checksum by '0.5', please DO use the original value

**Explanation of seq**

* The seq of update incremental messages is incrementing except during symbol maintenance.

Request Example

```json
{  
    "op": "subscribe",  
    "args": [  
        {  
            "instType": "SPOT",  
            "channel": "books5",  
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
| > channel | String | Yes | Channel name: `books/books1/books5/books15` |
| > instId | String | Yes | Product ID, e.g. ETHUSDT |

Response Example

```json
{  
  "event": "subscribe",  
  "arg": {  
    "instType": "SPOT",  
    "channel": "books5",  
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
| > channel | String | Channel name: `books/books1/books5/books15` |
| > instId | String | Product ID, e.g. ETHUSDT |
| code | String | Error code, returned only on error |
| msg | String | Error message |

Push Data

```json
{  
  "action": "snapshot",  
  "arg": {  
    "instType": "SPOT",  
    "channel": "books5",  
    "instId": "BTCUSDT"  
  },  
  "data": [  
    {  
      "asks": [  
        [  
          "26274.9",  
          "0.0009"  
        ],  
        [  
          "26275.0",  
          "0.0500"  
        ]  
      ],  
      "bids": [  
        [  
          "26274.8",  
          "0.0009"  
        ],  
        [  
          "26274.7",  
          "0.0027"  
        ]  
      ],  
      "checksum": 0,   
      "seq": 123,  
      "ts": "1695710946294"  
    }  
  ],  
  "ts": 1695710946294  
}
```

### Push Parameters[​](#push-parameters "Direct link to Push Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| arg | Object | Channels with successful subscription |
| > instType | String | Product type |
| > channel | String | Channel name: `books/books1/books5/books15` |
| > instId | String | Product ID, e.g. ETHUSDT |
| action | String | Push data action, `snapshot` or `update` |
| data | List<Object> | Subscription data |
| > instId | String | Product ID, e.g. ETHUSDT |
| > asks | List<String> | Seller depth |
| > bids | List<String> | Buyer depth |
| > ts | String | Matching engine timestamp(ms), e.g. 1597026383085 |
| > checksum | Long | Checksum |
| > seq | Long | Serial number. It increases when the order book is updated and can be used to determine whether there is out-of-order packets. |