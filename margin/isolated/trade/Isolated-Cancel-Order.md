# Isolated Cancel Order

Frequency limit: 10 times/1s (UID)

### Description[​](#description "Direct link to Description")

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/margin/isolated/cancel-order

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/margin/isolated/cancel-order" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*******" \  
   -H "ACCESS-PASSPHRASE:*****" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json" \     
   -d '   {    "symbol":"ETHUSDT",    "orderId":"121211212122"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| symbol | String | Yes | Trading pairs, BTCUSDT |
| orderId | String | No | Order ID Either orderId or clientOid is required |
| clientOid | String | No | Client customized ID Either orderId or clientOid is required |

Response Example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1695621708119,  
    "data": {  
        "orderId": "121211212122",  
        "clientOid": "121211212122"  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| orderId | String | Order ID |
| clientOid | String | Customized ID |