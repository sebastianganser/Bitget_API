# Cross Cancel Order

Frequency limit:10 times/1s (UID)

### Description[​](#description "Direct link to Description")

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/margin/crossed/cancel-order

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/margin/crossed/cancel-order"  -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*******" \  
   -H "ACCESS-PASSPHRASE:*****" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json"  -d '{"symbol": "BTCUSDT","orderId": "12234234321432"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| symbol | String | Yes | Trading pairs, like BTCUSDT |
| orderId | String | No | Order ID Either orderId or clientOid |
| clientOid | String | No | Client customized ID Either orderId or clientOid |

Response Example

```json
{  
    "code": "00000",  
    "data": {  
        "orderId": "121211212122",  
        "clientOid": "BITGET#121211212122"  
    },  
    "msg": "success",  
    "requestTime": 1627293504612  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| orderId | String | Order ID |
| clientOid | String | Customized ID |