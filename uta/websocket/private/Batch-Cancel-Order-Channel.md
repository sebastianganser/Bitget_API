# Batch Cancel Order

### Description[​](#description "Direct link to Description")

* Batch order cancellation allows partial success.
* In batch order cancellation, ensure that each call uses only orderId or clientOid for identification, and avoid mixing
  them. If orderId and clientOid are used together in one call, clientOid will be invalid.
* Please contact your BD or RM to apply for access permissions.

Request Example

```json
{  
    "args": [  
        {  
            "orderId": "xxxxxxxx"  
        },  
        {  
            "orderId": "xxxxxxxx"  
        }  
    ],  
    "id": "xxxxx-xxx-xxx-xxxx-xxxxxx",  
    "op": "trade",  
    "topic": "batch-cancel"  
}
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| op | String | Yes | Operation:   `trade` trade |
| id | String | Yes | Request identifier |
| topic | String | Yes | Topic `batch-cancel` |
| args | List<Object> | Yes | Channel list |
| > orderId | String | No | Order ID Either `clientOid` or `orderId` must be provided. If both are present or do not match, `orderId` will take priority |
| > clientOid | String | No | Client order ID  Either `clientOid` or `orderId` must be provided. If both are present or do not match, `orderId` will take priority |

Response Example

```json
{  
  "event": "trade",  
  "id": "bb553cc0-c1fa-454e-956d-c96c8d715760",  
  "topic": "batch-cancel",  
  "args": [  
    {  
      "code": "0",  
      "msg": "Success",  
      "orderId": "xxxxxxxxxxxxx",  
      "clientOid": "xxxxxxxxxxxxx"  
    },  
    {  
      "code": "25204",  
      "msg": "Order does not exist",  
      "orderId": "xxxxxxxxxxxxx",  
      "clientOid": "xxxxxxxxxxxxx"  
    }  
  ],  
  "code": "0",  
  "msg": "Success",  
  "ts": "1751980011084"  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameters | Type | Description |
| --- | --- | --- |
| event | String | Event `trade`/`error` |
| id | String | Request identifier |
| topic | String | Topic `batch-cancel` |
| args | List<Object> | Channel list |
| > code | String | Code |
| > msg | String | Message |
| > orderId | String | Order ID |
| > clientOid | String | Client order ID |
| code | String | Code |
| msg | String | Message |
| ts | String | Timestamp |