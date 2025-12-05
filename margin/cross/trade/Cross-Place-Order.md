# Cross Place Order

Rate Limit: 10 req/sec/UID

### Description[​](#description "Direct link to Description")

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/margin/crossed/place-order

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/margin/crossed/place-order"  -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*******" \  
   -H "ACCESS-PASSPHRASE:*****" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json"  -d '{"symbol": "BTCUSDT", "side":"buy", "orderType":"market", "force":"gtc", "quoteSize":"10000", "loanType":"normal"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| symbol | String | Yes | Trading pairs, like BTCUSDT |
| orderType | String | Yes | Order type limit: limit price market: market price |
| price | String | No | Price |
| loanType | String | Yes | Margin order model normal: place a normal order autoLoan place an order with auto-borrow autoRepay place an order with auto-repay autoLoanAndRepay place an order with auto-borrow and auto-repay |
| force | String | Yes | Time in force (invalid when `orderType` is `market`) gtc: Normal limit order, good till canceled post\_only: Post only fok: Fill or kill ioc: Immediate or cancel |
| baseSize | String | No | Must fill limit and market sell. Sell order presents quantity of based currency (the left coin). |
| quoteSize | String | No | Must fill market buy. Buy order presents quantity of quote currency (the right coin). |
| clientOid | String | No | Customized ID The idempotency time is 6 hours, only valid when orders are unfilled. |
| side | String | Yes | Direction sell: Sell buy: Buy |
| stpMode | String | No | STP Mode, default `none`   `none` not setting STP   `cancel_taker` cancel taker order   `cancel_maker` cancel maker order   `cancel_both` cancel both of taker and maker orders |

Response Example

```json
{  
    "code": "00000",  
    "data": {  
        "orderId": "121211212122",  
        "clientOid": "121211212122"  
    },  
    "msg": "success",  
    "requestTime": 1627293504612  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| orderId | String | Order ID |
| clientOid | String | Customized ID |