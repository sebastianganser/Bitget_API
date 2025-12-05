# Place Order Channel

### Description[​](#description "Direct link to Description")

1.Rate limit will be shared with Rest API   
2.Please connect to V2 Websocket domain: wss://ws.bitget.com/v2/ws/private   
3.So far websocket trading doesn't support placing batch orders  
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
         "channel":"place-order",  
         "params":{  
            "orderType":"limit",  
            "side":"buy",  
            "size":"1",  
            "price":"252",  
            "force":"gtc",  
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
| apiCode | String | No | API rebate identifier |
| args | List<Object> | Yes | List of channels to request subscription |
| > id | String | Yes | Unique Identifier Length<= 40 ("^[0-9A-Za-z\_:#\-+\s]\*$"); |
| > instType | String | Yes | Product line type `SPOT` |
| > instId | String | Yes | Product ID, e.g. `ETHUSDT` |
| > channel | String | Yes | Channel name, `place-order` |
| > params | Object | Yes |  |
| >> orderType | String | Yes | Order type `limit`: Limit order `market`: Market order |
| >> side | String | Yes | Order Direction `buy`: Buy `sell`: Sell |
| >> size | String | Yes | Amount For Limit and Market-Sell orders, it represents the number of base coins. For Market-Buy orders, it represents the number of quote coins. The decimal places of amount can be got trough Get Symbol Info interface |
| >> force | String | Yes | Execution strategy(It will be invalid when orderType is market)  `gtc`：Normal limit order, good till cancelled `post_only`：Post only `fok`：Fill or kill `ioc`：Immediate or cancel |
| >> price | String | No | Limit price The decimal places of price and the price step can be returned by the Get Symbol Info interface |
| >> clientOid | String | No | Custom order ID. |
| >> stpMode | String | No | STP Mode(Self Trade Prevention) `none`：not setting STP(default) `cancel_taker`：cancel taker order `cancel_maker`：cancel maker order `cancel_both`：cancel both of taker and maker orders |

Response

```json
{  
  "event":"trade",  
  "arg":[  
    {  
      "id":"xxxxx-xxx-xxx-xxxx-xxxxxx",  
      "instType":"SPOT",  
      "channel":"place-order",  
      "instId":"BTCUSDT",  
      "params":{  
        "orderId":"xxxxxxxx",  
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
| > channel | String | Channel name, `place-order` |
| > params | Object |  |
| >> OrderId | String | Order ID. |
| >> orderType | String | Order type `limit`: Limit order `market`: Market order |
| >> side | String | Order Direction `buy`: Buy `sell`: Sell |
| >> size | String | Amount For Limit and Market-Sell orders, it represents the number of base coins. For Market-Buy orders, it represents the number of quote coins. The decimal places of amount can be got trough Get Symbol Info interface |
| >> force | String | Execution strategy(It will be invalid when orderType is market)  `gtc`：Normal limit order, good till cancelled `post_only`：Post only `fok`：Fill or kill `ioc`：Immediate or cancel |
| >> price | String | Limit price The decimal places of price and the price step can be returned by the Get Symbol Info interface |
| >> clientOid | String | Custom order ID. |
| >> stpMode | String | STP Mode(Self Trade Prevention) `none`：not setting STP(default) `cancel_taker`：cancel taker order `cancel_maker`：cancel maker order `cancel_both`：cancel both of taker and maker orders |
| code | String | code |
| msg | String | msg |