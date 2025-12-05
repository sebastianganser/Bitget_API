# Cancel Order Channel

### Description[​](#description "Direct link to Description")

1.Rate limit will be shared with Rest API   
2.Please connect to V2 Websocket domain: wss://ws.bitget.com/v2/ws/private   
3.So far websocket trading doesn't support canceling batch orders  
4.Please contact your BD or RM to apply for access permissions

Request

```json
{  
   "op":"trade",  
   "args":[  
      {  
         "id":"xxxxx-xxx-xxx-xxxx-xxxxxx",  
         "instType":"SPOT",  
         "instId":"BTCUSDT",  
         "channel":"cancel-order",  
         "params":{  
            "orderId":"xxxxxxxxx",  
            "clientOid":"xxxxx-xxx-xxx-xxxx-xxxxxx"  
         }  
      }  
   ]  
}
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| op | String | Yes | "trade" |
| args | List<Object> | Yes | List of channels to request subscription |
| > id | String | Yes | Unique Identifier Length<= 40 ("^[0-9A-Za-z\_:#\-+\s]\*$"); |
| > instType | String | Yes | Product line type `SPOT` |
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
      "instType":"SPOT",  
      "channel":"cancel-order",  
      "instId":"BTCUSDT",  
      "params":{  
        "orderId":"xxxxxxxxxxx",  
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
| > instType | String | Product line type `SPOT` |
| > instId | String | Product ID, e.g. `ETHUSDT` |
| > channel | String | Channel name, `cancel-order` |
| > params | Object |  |
| >> orderId | String | Order ID   Either `orderId` or `clientOid` is required.If both are present, orderId prevails. |
| >> clientOid | String | Custom order ID   Either `orderId` or `clientOid` is required.If both are present, orderId prevails. |
| code | String | code |
| msg | String | msg |