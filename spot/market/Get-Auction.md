# Get Call Auction information

Frequency limit: 20 times/1s (IP)

### Description[​](#description "Direct link to Description")

Get Call Auction information

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/spot/market/auction

Request Example

```json
curl "https://api.bitget.com/api/v2/spot/market/auction?symbol=BTCUSDT"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| symbol | String | Yes | Trading pair |

Response Example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1728875148294,  
    "data": {  
        "stage": "stage_1",  
        "stageEndTime": "1728876900000",  
        "estOpeningPrice": null,  
        "matchedVolume": null,  
        "auctionEndTime": "1728877500000"  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| stage | String | Call Auction  `pre_market` pre market `stage_1` Auction 1 `stage_2` Auction 2 `stage_3` Auction 3 `success` Auction success `failure` Auction failed |
| stageEndTime | String | Current phase end time , millseconds |
| estOpeningPrice | String | Estimated Opening Price |
| matchedVolume | String | Matched Volume ,base coin |
| auctionEndTime | String | Call Auction end time , millseconds |