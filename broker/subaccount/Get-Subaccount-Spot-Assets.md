# Get Subaccount Spot Assets

Frequency limit：10 times/1s (User ID)

### Description[​](#description "Direct link to Description")

Get subaccount spot assets

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/broker/account/subaccount-spot-assets

Request Example

```json
curl "https://api.bitget.com/api/v2/broker/account/subaccount-spot-assets?subUid=111111" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*" \  
  -H "ACCESS-PASSPHRASE:*" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json"
```

### HTTP Request[​](#http-request-1 "Direct link to HTTP Request")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| subUid | String | Yes | Subaccount user id |
| coin | String | No | Token name, e.g. USDT |
| assetType | String | No | Asset type hold\_only: Position coin all: All coins This field is used used for querying the positions of multiple coins. The default value is "hold\_only" When only assetType is entered without coin, results of all eligible coins are returned. When both coin and assetType are entered, coin has higher priority. |

Response example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1695785115457,  
    "data": {  
        "assetsList": [  
            {  
                "coin": "BTC",  
                "available": "100.00000000",  
                "frozen": "0.00000000",  
                "locked": "0.00000000",  
                "uTime": "1692105973000"  
            },  
            {  
                "coin": "USDT",  
                "available": "100.00000000",  
                "frozen": "0.00000000",  
                "locked": "0.00000000",  
                "uTime": "1692105971000"  
            },  
            {  
                "coin": "ETH",  
                "available": "100000.00000000",  
                "frozen": "0.00000000",  
                "locked": "0.00000000",  
                "uTime": "1695024539000"  
            }  
        ]  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| assetsList | List<Object> | Spot asset list |
| coin | String | Token name |
| available | String | Available assets |
| frozen | String | Amount of frozen assets Usually frozen when the order is placed |
| locked | String | Amount of locked assets Locked assests required to become a fiat merchants, etc. |
| uTime | String | Update time |