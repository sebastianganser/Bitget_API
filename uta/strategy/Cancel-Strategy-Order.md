# Cancel Strategy Order

### Description[​](#description "Direct link to Description")

Cancel strategy order

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v3/trade/cancel-strategy-order
* Speed limit is 10 times/s (UID)
* Permission: UTA trade (read & write)

Request

```json
curl -X POST "https://api.bitget.com/api/v3/trade/cancel-strategy-order" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*" \  
  -H "ACCESS-PASSPHRASE:*" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:zh-CN" \  
  -H "Content-Type: application/json" \  
  -d '{"orderId":"111111111111111111"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| orderId | String | Yes | Order ID Either orderId or clientOid must be provided If both orderId and clientOid are provided simultaneously, orderId takes higher priority |
| clientOid | String | No | Client order ID  Either orderId or clientOid must be provided If both orderId and clientOid are provided simultaneously, orderId takes higher priority |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1695806875837,  
  "data": null  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| code | String | Code |
| msg | String | Msg |
| requestTime | String | Timestamp |