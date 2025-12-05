# Get Liquidation Price

Rate limit: 20 req/sec/UID

### Description[​](#description "Direct link to Description")

Get Liquidation Price

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/mix/account/liq-price

Request

```json
curl "https://api.bitget.com/api/v2/mix/account/liq-price?productType=USDT-FUTURES&symbol=ETHUSDT&posSide=long&orderType=market&marginCoin=USDT&openAmount=50" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| symbol | String | Yes | Symbol，e.g.: ETHUSDT |
| productType | String | Yes | Product type `USDT-FUTURES` USDT Futures `COIN-FUTURES` Coin Futures `USDC-FUTURES` USDC Futures |
| marginCoin | String | Yes | Margin Coin |
| posSide | String | Yes | Position side `long`Long `short`Short |
| orderType | String | Yes | orderType `limit`Limit order `market`Market order |
| openAmount | String | Yes | Margin amount for opening position |
| openPrice | String | No | Opening price Required when `orderType=limit` |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1762437950669,  
  "data": {  
    "liqPrice": "-5025939.4855934659933227"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| liqPrice | String | Liquidation Price |