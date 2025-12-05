# Isolated Place Order

Rate Limit: 10 req/sec/UID

### Description[​](#description "Direct link to Description")

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/margin/isolated/place-order

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/margin/isolated/place-order" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*******" \  
   -H "ACCESS-PASSPHRASE:*****" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json" \     
   -d '   {    "symbol": "ETHUSDT",    "side": "buy",    "price":"1796.5",    "orderType": "limit",    "force": "gtc",    "baseSize":"0.1",    "loanType":"normal"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| symbol | String | Yes | Trading pairs, BTCUSDT |
| orderType | String | Yes | Order type limit market |
| price | String | No | Price |
| loanType | String | Yes | Margin order model normal: Normal order autoLoan: auto-borrow order autoRepay: auto-repay order autoLoanAndRepay: auto-borrow and auto-repay order |
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
  "requestTime": 1695621004679,  
  "data": {  
    "orderId": "121211212122",  
    "clientOid": "121211212122"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| orderId | String | Order ID |
| clientOid | String | Customized ID |