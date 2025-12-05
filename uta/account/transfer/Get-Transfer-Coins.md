# Get Transferable Coins

### Description[​](#description "Direct link to Description")

Query transferable coins **between Classic and UTA accounts**.   
*Classic accounts include Spot, Isolated Margin, Cross Margin, USDT Futures, USDC Futures, Coin-M Futures, and P2P accounts*

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/account/transferable-coins
* Rate limit: 10/sec/UID
* Permission: UTA mgt. (read)

Request

```json
curl "https://api.bitget.com/api/v3/account/transferable-coins?fromType=uta&toType=spot" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| fromType | String | Yes | From (source) account type `spot` Spot account/Funding account `p2p` P2P account/OTC account `coin_futures` Coin-M futures account `usdt_futures` USDT futures account `usdc_futures` USDC futures account `crossed_margin` Cross margin account `isolated_margin` Isolated margin account `uta` Unified trading account |
| toType | String | Yes | To (target) account type `spot` Spot account/Funding account `p2p` P2P account/OTC account `coin_futures` Coin-M futures account `usdt_futures` USDT futures account `usdc_futures` USDC futures account `crossed_margin` Cross margin account `isolated_margin` Isolated margin account `uta` Unified trading account |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1730189276579,  
  "data": [  
        "USDT"  
    ]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| >index [0] | String | Transferable coin |