# Modify Order

### Description[​](#description "Direct link to Description")

Request

```json
{  
    "args": [  
        {  
            "autoCancel": "yes",  
            "clientId": "135423791666666666",  
            "orderId": "1354237910666666666",  
            "price": "5",  
            "qty": "2",  
            "symbol":"BTCUSDT"  
        }  
    ],  
    "id": "ae5ea6df-215f-4750-a700-d487d03ac020",  
    "op": "trade",  
    "category": "usdt-futures",  
    "topic": "modify-order"  
}
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| op | String | Yes | Operation:   `trade` |
| id | String | Yes | Request identifier |
| topic | String | Yes | Topic  `modify-order` |
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
  "id": "ae5ea6df-215f-4750-a700-d487d03ac020",  
  "topic": "modify-order",  
  "args": [  
    {  
      "orderId": "135423791666666666",  
      "clientOid": "1354237910666666666"  
    }  
  ],  
  "code": "0",  
  "msg": "Success",  
  "ts": "1758601481031"  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameters | Type | Description |
| --- | --- | --- |
| event | String | Event `trade`/`error` |
| id | String | Request identifier |
| topic | String | Topic `modify-order` |
| args | List<Object> | Channel list |
| > orderId | String | Order ID |
| > clientOid | String | Client order ID |
| > code | String | Code |
| > msg | String | Message |
| code | String | Code |
| msg | String | Message |
| ts | String | Timestamp |