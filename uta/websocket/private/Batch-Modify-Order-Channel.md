# Batch Modify Order

### Description[​](#description "Direct link to Description")

Request

```json
{  
    "args": [  
        {  
            "autoCancel": "yes",  
            "clientId": "1354237913333333333",  
            "orderId": "1354237910333333333",  
            "price": "5",  
            "qty": "5"  
        },  
        {  
            "autoCancel": "yes",  
            "clientId": "1354240301222222222",  
            "orderId": "1354240301222222222",  
            "price": "5",  
            "qty": "2"  
        }  
    ],  
    "id": "63210d1e-b400-47c7-afc6-323018afe71a",  
    "op": "trade",  
    "topic": "batch-modify"  
}
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| op | String | Yes | Operation:   `trade` |
| id | String | Yes | Request identifier |
| topic | String | Yes | Topic  `batch-modify` |
| category | String | No | Business line  `SPOT` Spot trading `MARGIN` Margin trading  `USDT-FUTURES` USDT Futures `COIN-FUTURES` Coin-M futures `USDC-FUTURES` USDC Futures |
| args | List<Object> | Yes | Channel list |
| > orderId | String | No | Order ID  Either orderId or clientOid is required. If both orderId and clientOid are passed simultaneously, orderId takes higher priority, and the clientOid parameter will be ignored. |
| > clientOid | String | No | Client order ID Either orderId or clientOid is required. If both orderId and clientOid are passed simultaneously, orderId takes higher priority, and the clientOid parameter will be ignored. |
| > qty | String | No | Order quantity - Spot  For market buy orders, the unit is quote coin  For limit and market sell orders, the unit is base coin  - Futures The unit is base coin |
| > price | String | No | Order price This field is required when orderType is `limit` |
| > autoCancel | String | No | Will the original order be canceled if the order modification fails `yes`: Cancel  `no`: Not cancel（default） |
| > symbol | String | No | Symbol name |

Response

```json
{  
  "event": "trade",  
  "id": "63210d1e-b400-47c7-afc6-323018afe71a",  
  "topic": "batch-modify",  
  "args": [  
    {  
      "code": "25571",  
      "msg": "The modification price and qty is the same as the original value. Please adjust and try again.",  
      "orderId": "1354237913333333333",  
      "clientOid": "1354237910333333333"  
    },  
    {  
      "code": "0",  
      "msg": "Success",  
      "orderId": "1354240301222222222",  
      "clientOid": "1354240301222222222"  
    }  
  ],  
  "code": "0",  
  "msg": "Success",  
  "ts": "1758602036638"  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameters | Type | Description |
| --- | --- | --- |
| event | String | Event `trade`/`error` |
| id | String | Request identifier |
| topic | String | Topic `batch-modify` |
| args | List<Object> | Channel list |
| > orderId | String | Order ID |
| > clientOid | String | Client order ID |
| > code | String | Code |
| > msg | String | Message |
| code | String | Code |
| msg | String | Message |
| ts | String | Timestamp |