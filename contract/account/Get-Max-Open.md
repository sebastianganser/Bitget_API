# Get Max Openable Quantity

Rate limit: 20 req/sec/UID

### Description[​](#description "Direct link to Description")

The result for the estimated openable quantity includes current positions and existing orders.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/mix/account/max-open

Request

```json
curl "https://api.bitget.com/api/v2/mix/account/max-open?productType=USDT-FUTURES&symbol=ETHUSDT&posSide=long&orderType=market&marginCoin=USDT&openAmount=50" \  
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
| openPrice | String | No | Opening price Required when `orderType=limit` |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1762438504409,  
  "data": {  
    "maxOpen": "17563.78"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| maxOpen | String | Max Openable Quantity |