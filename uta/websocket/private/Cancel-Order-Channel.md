# Cancel Order

### Description[​](#description "Direct link to Description")

* Please contact your BD or RM to apply for access permissions.

Request Example

```json
{  
    "args": [  
        {  
            "orderId": "xxxxxxxxxxxxxxxxxx",  
            "clientOid": "xxxxxxxxxxxxxxxxxx"  
        }  
    ],  
    "id": "c8a1999c-1f82-409d-870e-f40ff49c4072",  
    "op": "trade",  
    "topic": "cancel-order"  
}
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| op | String | Yes | Operation:   `trade` trade |
| id | String | Yes | Request identifier |
| topic | String | Yes | opic `cancel-order` |
| category | String | No | Category  `spot`Spot `margin` Margin  `usdt-futures` USDT futures `coin-futures` Coin futures `usdc-futures` USDC futures |
| args | List<Object> | Yes | Channel list |
| > orderId | String | No | Order ID Either `clientOid` or `orderId` must be provided. If both are present or do not match, `orderId` will take priority |
| > clientOid | String | No | Client order ID  Either `clientOid` or `orderId` must be provided. If both are present or do not match, `orderId` will take priority |

Response

```json
{  
  "event": "trade",  
  "id": "1750034870205",  
  "topic": "cancel-order",  
  "args": [  
    {  
      "orderId": "xxxxxxxx",  
      "clientOid": "xxxxxxxx"  
    }  
  ],  
  "code": "0",  
  "msg": "Success",  
  "ts": "1750034870597"  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameters | Type | Description |
| --- | --- | --- |
| event | String | Event `trade`/`error` |
| id | String | Request identifier |
| topic | String | Topic `cancel-order` cancel-order |
| args | List<Object> | Channel list |
| > orderId | String | Order ID |
| > clientOid | String | Client order ID |
| code | String | Code |
| msg | String | Message |
| ts | String | Timestamp |