# Get Position ADL Rank

### Description[​](#description "Direct link to Description")

Get Position ADL Rank

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/position/adlRank
* Rate limit: 1/sec/UID
* Permission: UTA trade (read & write)

Request

```json
curl "https://api.bitget.com/api/v3/position/adlRank" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*" \  
  -H "ACCESS-PASSPHRASE:*" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:zh-CN" \  
  -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

N/A

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1754035547922,  
  "data": [  
    {  
      "symbol": "MOVEUSDT",  
      "marginCoin": "USDT",  
      "adlRank": "0.4872",  
      "holdSide": "long"  
    }  
  ]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| symbol | String | Symbol |
| marginCoin | String | Margin Coin |
| adlRank | String | ADL Ranking The ranking of your current position in the auto-deleveraging sequence. When an auto-deleveraging event occurs in the market, the closer the value is to 1, the higher the probability that your position will be reduced |
| holdSide | String | Position Direction  `long` long position  `short` short position |