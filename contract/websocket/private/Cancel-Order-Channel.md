# Cancel Order Channel

### Description[​](#description "Direct link to Description")

* Cancel order
* Please contact your BD or RM to apply for access permissions

Request

```json
{  
   "args":[  
      {  
         "channel":"cancel-order",  
         "id":"xxxxx-xxx-xxx-xxxx-xxxxxx",  
         "instId":"BTCUSDT",  
         "instType":"USDT-FUTURES",  
         "params":{  
            "orderId":"xxxxxxxxxx",  
            "clientOid":"xxxxx-xxx-xxx-xxxx-xxxxxx"  
         }  
      }  
   ],  
   "op":"trade"  
}
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| op | String | Yes | "trade" |
| args | List<Object> | Yes | List of channels to request subscription |
| > id | String | Yes | Unique Identifier Length<= 40 ("^[0-9A-Za-z\_:#\-+\s]\*$"); |
| > instType | String | Yes | Product line type `USDT-FUTURES` |
| > instId | String | Yes | Product ID, e.g. `ETHUSDT` |
| > channel | String | Yes | Channel name, `cancel-order` |
| > params | Object | Yes |  |
| >> orderId | String | No | Order ID   Either `orderId` or `clientOid` is required.If both are present, orderId prevails. |
| >> clientOid | String | No | Custom order ID   Either `orderId` or `clientOid` is required.If both are present, orderId prevails. |

Fail

```json
{  
  "event":"trade",  
  "arg":[  
    {  
      "id":"xxxxx-xxx-xxx-xxxx-xxxxxx",  
      "instType":"USDT-FUTURES",  
      "channel":"cancel-order",  
      "instId":"BTCUSDT",  
      "params":{  
        "orderId":"xxxxxxxxx",  
        "clientOid":"xxxxx-xxx-xxx-xxxx-xxxxxx"  
      }  
    }  
  ],  
  "code":0,  
  "msg":"Success"  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| event | String | Event `trade`  `error` |
| arg | Object | Channel |
| > id | String | Unique Identifier Length<= 40 ("^[0-9A-Za-z\_:#\-+\s]\*$"); |
| > instType | String | Product line type `USDT-FUTURES` |
| > instId | String | Product ID, e.g. `ETHUSDT` |
| > channel | String | Channel name, `cancel-order` |
| > params | Object |  |
| >> orderId | String | Order ID   Either `orderId` or `clientOid` is required.If both are present, orderId prevails. |
| >> clientOid | String | Custom order ID   Either `orderId` or `clientOid` is required.If both are present, orderId prevails. |
| code | String | code |
| msg | String | msg |