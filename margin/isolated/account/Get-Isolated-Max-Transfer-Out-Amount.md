# Get Isolated Max Transferable

Frequency limit: 10 times/1s (UID)

### Description[​](#description "Direct link to Description")

Get Isolated Max Transferable Amount

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/margin/isolated/account/max-transfer-out-amount

Request Example

```json
curl "https://api.bitget.com/api/v2/margin/isolated/account/max-transfer-out-amount?symbol=BTCUSDT" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*******" \  
   -H "ACCESS-PASSPHRASE:*****" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| symbol | String | Yes | Trading pairs, like BTCUSDT |

Response Example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1695618856403,  
  "data": {  
    "baseCoin": "BTC",  
    "symbol": "BTCUSDT",  
    "baseCoinMaxTransferOutAmount": "199999",  
    "quoteCoin": "USDT",  
    "quoteCoinMaxTransferOutAmount": "1000000"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| symbol | String | Trading pair |
| baseCoin | String | Base coin |
| quoteCoin | String | Quote coin |
| baseCoinMaxTransferOutAmount | String | Maximum transferable amount for base coin |
| quoteCoinMaxTransferOutAmount | String | Maximum transferable amount for quote coin |