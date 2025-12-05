# Auction Channel

### Description[​](#description "Direct link to Description")

Get the product's Call Auction information. Frequency of data push: 100ms ~ 300ms

Request Example

```json
{  
    "op": "subscribe",  
    "args": [  
        {  
            "instType": "SPOT",  
            "channel": "auction",  
            "instId": "BTCUSDT"  
        }  
    ]  
}
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| op | String | Yes | Operation, subscribe unsubscribe |
| args | List<Object> | Yes | List of channels to subscribe to |
| > instType | String | Yes | Product Line Type |
| > channel | String | Yes | Channel name: `auction` |
| > instId | String | Yes | Product id For example: ETHUSDT |

Response Example

```json
{  
    "event": "subscribe",  
    "arg": {  
        "instType": "SPOT",  
        "channel": "auction",  
        "instId": "BTCUSDT"  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| event | String | is an   event, |
| arg | Object | No Channel to subscribe to |
| > instType | String | Is product type |
| > channel | String | is channel name |
| > instId | String | is product id. For example: BTCUSDT |
| code | String | Error code, returned only on error |
| msg | String | Error message |

Push Data

```json
{  
    "action": "snapshot",  
    "arg": {  
        "instType": "SPOT",  
        "channel": "auction",  
        "instId": "BTCUSDT"  
    },  
    "data": [  
        {  
            "stage": "stage_1",  
            "stageEndTime": "1728876900000",  
            "estOpeningPrice": null,  
            "matchedVolume": null,  
            "auctionEndTime": "1728877500000"  
        }  
    ],  
    "ts": 1695711090682  
}
```

### Push Parameters[​](#push-parameters "Direct link to Push Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| arg | Object | Successfully subscribed channel |
| > instType | String | Product Type |
| > channel | String | Channel name |
| > instId | String | Product id For example: ETHUSDT |
| action | String | Push data action, `snapshot` or `update` |
| data | List<Object> | Subscribed data |
| > stage | String | Call Auction  `pre_market` pre market `stage_1` Auction 1 `stage_2` Auction 2 `stage_3` Auction 3 `success` Auction success `failure` Auction failed |
| > stageEndTime | String | Current phase end time , millseconds |
| > estOpeningPrice | String | Estimated Opening Price |
| > matchedVolume | String | Matched Volume ,base coin |
| >auctionEndTime | String | Call Auction end time , millseconds |