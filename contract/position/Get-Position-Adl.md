# Get Position Adl Rank

5times/S （uid）

### Description[​](#description "Direct link to Description")

Query Account Position ADL Rank

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/mix/position/adlRank

Request

```json
curl "https://api.bitget.com/api/v2/mix/position/adlRank?productType=USDT-FUTURES" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json"
```

### Request Parameter[​](#request-parameter "Direct link to Request Parameter")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| productType | String | Yes | Product type, default:`USDT-FUTURES`,  `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1753775486724,  
  "data": [  
    {  
      "symbol": "MOVEUSDT",  
      "marginCoin": "USDT",  
      "adlRank": "0.2248",  
      "rank": "0.7752",  
      "holdSide": "long"  
    }  
  ]  
}
```

### Response Parameter[​](#response-parameter "Direct link to Response Parameter")

| Parameter | Type | Description |
| --- | --- | --- |
| symbol | String | Trading pair |
| marginCoin | String | Margin coin |
| adlRank (Deprecated) | String | This indicator shows your position in the ADL queue. the further ahead you are in the queue, the higher the possibility that your position may be reduced in the event of an auto-deleveraging |
| rank | String | Current position's ADL sequence rank. Closer to 1, more prone to ADL during market events. |
| holdSide | String | Position direction long: long position  short: short position |