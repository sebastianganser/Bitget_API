# Cancel Isolated Orders in Batch

Rate limit: 10 req/sec/UID

### Description[​](#description "Direct link to Description")

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/margin/isolated/batch-cancel-order

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/margin/isolated/batch-cancel-order" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*******" \  
   -H "ACCESS-PASSPHRASE:*****" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json" \     
   -d '   {    "symbol": "BTCUSDT",    "orderIdList": [{        "orderId":"121211212122",        "clientId":"121211212122"    }    ]}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| symbol | String | Yes | Trading pairs, BTCUSDT |
| orderIdList | List | No | Order ID list  Either orderId or clientOid is required |
| > orderId | String | No | Order ID  Either orderId or clientOid |
| > clientOid | String | No | Client customized ID  Either orderId or clientOid |

Response Example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1695622930742,  
  "data": {  
    "successList": [  
      {  
        "orderId": "121211212122",  
        "clientOid": "121211212122"  
      }  
    ],  
    "failureList": [  
    ]  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| successList | Array | Successful order number |
| > orderId | String | Order ID |
| > clientOid | String | Client customized ID |
| failureList | Array | Failed order number |
| > clientOid | String | Client customized ID |
| > errorMsg | String | Error information |