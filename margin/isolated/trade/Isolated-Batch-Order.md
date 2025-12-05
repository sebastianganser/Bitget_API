# Isolated Batch Orders

Frequency limit: 10 times/1s (UID)

### Description[​](#description "Direct link to Description")

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/margin/isolated/batch-place-order

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/margin/isolated/batch-place-order" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*******" \  
   -H "ACCESS-PASSPHRASE:*****" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json" \     
   -d '   {    "symbol":"BTCUSDT",    "orderList": [        {    "side": "buy",        "orderType": "market",    "force": "gtc",        "quoteSize":"110",    "loanType":"normal"}    ]}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| symbol | String | Yes | Trading pairs, BTCUSDT |
| orderList | List | Yes | Order Entries |
| orderType | String | Yes | Order type limit market |
| price | String | No | Price |
| loanType | String | Yes | Margin order model normal: Normal order autoLoan: auto-borrow order autoRepay: auto-repay order autoLoanAndRepay: auto-borrow and auto-repay order timeInforce |
| force | String | Yes | Time in force (invalid when `orderType` is `market`) gtc: normal limit order, good till canceled post\_only: Post only fok: Fill or kill ioc: Immediate or cancel |
| baseSize | String | No | Limit and Market sell are required. Sell orders represent the number of baseCoins (left coin). |
| quoteSize | String | No | market buy is required, the buy order represents the number of quote coins (right coin). |
| clientOid | String | No | Customized ID |
| side | String | Yes | Direction sell: Sell buy: Buy |
| stpMode | String | No | STP Mode, default `none`   `none` not setting STP   `cancel_taker` cancel taker order   `cancel_maker` cancel maker order   `cancel_both` cancel both of taker and maker orders |

Response Example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1695621286952,  
  "data": {  
    "successList": [  
      {  
        "orderId": "121211212122",  
        "clientOid": "121211212122"  
      }  
    ],  
    "failureList": [  
    ]  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| successList | Array | Successful order number |
| > orderId | String | Order ID |
| > clientOid | String | Client customized ID |
| failureList | Array | Failed order number |
| > clientOid | String | Client customized ID |
| > errorMsg | String | Error information |