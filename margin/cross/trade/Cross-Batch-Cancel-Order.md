# Cross Batch Cancel Orders

Frequency limit:10 times/1s (UID)

### Description[​](#description "Direct link to Description")

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/margin/crossed/batch-cancel-order

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/margin/crossed/batch-cancel-order"  -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*******" \  
   -H "ACCESS-PASSPHRASE:*****" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json"  -d '{"symbol": "BTCUSDT","orderIdList": [{"orderId":"11232132134"},{"clientOid":"mytestOid"}]}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| symbol | String | Yes | Trading pairs, like BTCUSDT |
| orderIdList | List | yes | Order ID list  Either orderId or clientOid |
| > orderId | String | No | Order ID  Either orderId or clientOid |
| > clientOid | String | No | Client customized ID  Either orderId or clientOid |

Response Example

```json
{  
    "code": "00000",  
    "data": {  
        "successList": [  
            {  
                "orderId": "121211212122",  
                "clientOid": "BITGET#121211212122"  
            }  
        ],  
        "failureList": [  
            {  
                "orderId": "121211212122",  
                "clientOid": "BITGET#121211212122",  
                "errorMsg": "Order Cancelled"  
            }  
        ]  
    },  
    "msg": "success",  
    "requestTime": 1627293504612  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| successList | Array | Successful order array |
| > orderId | String | Order ID |
| > clientOid | String | Client customized ID |
| failureList | Array | Failed order array |
| > orderId | String | Order ID |
| > clientOid | String | Client customized ID |
| > errorMsg | String | Error information |