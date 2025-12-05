# Place Order Channel

### Description[​](#description "Direct link to Description")

* Ignore the `tradeSide` parameter when position mode is in one-way-mode
* hedge position mode: Open long: `"side"=buy, "tradeSide"=open`; Close long: `"side"=buy, "tradeSide"=close`; Open short: `"side"=sell, "tradeSide"=open`; Close short: `"side"=sell, "tradeSide"=close`; one-way position mode: "side"=buy and sell, tradeSide: ignore；
* Please contact your BD or RM to apply for access permissions

Request Example

```json
{  
   "args":[  
      {  
         "channel":"place-order",  
         "id":"xxxxx-xxx-xxx-xxxx-xxxxxx",  
         "instId":"BTCUSDT",  
         "instType":"USDT-FUTURES",  
         "params":{  
            "orderType":"limit",  
            "side":"buy",  
            "size":"2",  
            "tradeSide":"open",  
            "price":"501",  
            "marginCoin":"USDT",  
            "force":"gtc",  
            "marginMode":"crossed",  
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
| apiCode | String | No | API rebate identifier |
| args | List<Object> | Yes | List of channels to request subscription |
| > id | String | Yes | Unique Identifier Length<= 40 ("^[0-9A-Za-z\_:#\-+\s]\*$"); |
| > instType | String | Yes | Product line type `USDT-FUTURES` |
| > instId | String | Yes | Product ID, e.g. `ETHUSDT` |
| > channel | String | Yes | Channel name, `place-order` |
| > params | Object | Yes |  |
| >> orderType | String | Yes | Order type `limit`: Limit order `market`: Market order |
| >> side | String | Yes | Trade side `buy`: Buy(one-way-mode); Long position direction(hedge-mode) `sell`: Sell(one-way-mode); Short position direction(hedge-mode) |
| >> size | String | Yes | Amount (base coin) To get the decimal places of size:Get Contract Config |
| >> force | String | Yes | Execution strategy(It will be invalid when orderType is market)  `gtc`：Normal limit order, good till cancelled `post_only`：Post only `fok`：Fill or kill `ioc`：Immediate or cancel |
| >> price | String | No | Limit price The decimal places of price and the price step can be returned by the Get Symbol Info interface |
| >> clientOid | String | No | Custom order ID |
| >> marginCoin | String | Yes | Margin coin(capitalized) |
| >> marginMode | String | Yes | Position mode `isolated`: isolated margin `crossed`: crossed margin |
| >> tradeSide | String | No | Trade type Only required in hedge-mode `open`: Open position `close`: Close position |
| >> reduceOnly | String | No | Whether or not to just reduce the position: `YES, NO` Default: `NO`. Applicable only in one-way-position mode |
| >> presetStopSurplusPrice | String | No | Take-profit value No take-profit is set if the field is empty. |
| >> presetStopLossPrice | String | No | Stop-loss value No stop-loss is set if the field is empty. |
| >> stpMode | String | No | STP Mode(Self Trade Prevention) `none`：not setting STP(default) `cancel_taker`：cancel taker order `cancel_maker`：cancel maker order `cancel_both`：cancel both of taker and maker orders |

Fail

```json
{  
  "event":"trade",  
  "arg":[  
    {  
      "id":"xxxxx-xxx-xxx-xxxx-xxxxxx",  
      "instType":"USDT-FUTURES",  
      "channel":"place-order",  
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
| > instType | String | Product line type `USDT-FUTURES` |
| > instId | String | Product ID, e.g. `ETHUSDT` |
| > channel | String | Channel name, `place-order` |
| > params | Object |  |
| >> orderType | String | Order type `limit`: Limit order `market`: Market order |
| >> OrderId | String | Order ID. |
| >> side | String | Trade side `buy`: Buy(one-way-mode); Long position direction(hedge-mode) `sell`: Sell(one-way-mode); Short position direction(hedge-mode) |
| >> size | String | Amount (base coin) To get the decimal places of size:Get Contract Config |
| >> force | String | Execution strategy(It will be invalid when orderType is market)  `gtc`：Normal limit order, good till cancelled `post_only`：Post only `fok`：Fill or kill `ioc`：Immediate or cancel |
| >> price | String | Limit price The decimal places of price and the price step can be returned by the Get Symbol Info interface |
| >> clientOid | String | Custom order ID |
| >> marginCoin | String | Margin coin(capitalized) |
| >> marginMode | String | Position mode `isolated`: isolated margin `crossed`: crossed margin |
| >> tradeSide | String | Trade type Only required in hedge-mode `open`: Open position `close`: Close position |
| >> reduceOnly | String | Whether or not to just reduce the position: `YES, NO` Default: `NO`. Applicable only in one-way-position mode |
| >> presetStopSurplusPrice | String | Take-profit value No take-profit is set if the field is empty. |
| >> presetStopLossPrice | String | Stop-loss value No stop-loss is set if the field is empty. |
| >> stpMode | String | STP Mode(Self Trade Prevention) `none`：not setting STP(default) `cancel_taker`：cancel taker order `cancel_maker`：cancel maker order `cancel_both`：cancel both of taker and maker orders |
| code | String | code |
| msg | String | msg |