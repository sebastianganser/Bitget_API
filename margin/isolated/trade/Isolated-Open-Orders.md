# Get Isolated Current Orders

Rate limit: 10 req/sec/UID

### Description[​](#description "Direct link to Description")

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/margin/isolated/open-orders

Request Example

```json
curl "https://api.bitget.com/api/v2/margin/isolated/open-orders?symbol=ETHUSDT&startTime=1695336324000"  -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*******" \  
   -H "ACCESS-PASSPHRASE:*****" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| symbol | String | Yes | Trading pairs, BTCUSDT |
| orderId | String | No | Order ID |
| clientOid | String | No | Client customized ID |
| startTime | String | Yes | Start time, Unix millisecond timestamps |
| endTime | String | No | End time, Unix millisecond timestamps |
| limit | String | No | Number of queries The default value is 100 entries and the maximum value is 500 entries. |

Response Example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1695623147774,  
  "data": {  
    "orderList": [  
      {  
        "symbol": "ETHUSDT",  
        "orderType": "limit",  
        "enterPointSource": "API",  
        "orderId": "121211212122",  
        "clientOid": "121211212122",  
        "loanType": "normal",  
        "price": "1410.5",  
        "side": "buy",  
        "status": "live",  
        "baseSize": "0.1",  
        "quoteSize": "141.05",  
        "priceAvg": "0",  
        "size": "0",  
        "amount": "0",  
        "force": "gtc",  
        "cTime": "1695623143333",  
        "uTime": "1695623143333"  
      }  
    ],  
    "maxId": "121211212122",  
    "minId": "121211212122"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| orderList | List | Order list |
| > symbol | String | Trading pair |
| > orderId | String | Order no. |
| > clientOid | String | Client customized ID |
| > size | String | Filled quantity |
| > priceAvg | String | Filled price |
| > amount | String | Filled quantity |
| > force | String | Order strategy gtc: normal limit order, good till canceled post\_only: Post only fok: Fill or kill ioc: Immediate or cancel |
| > price | String | Order price |
| > enterPointSource | String | Order source WEB: WEB client IOS: IOS client ANDROID: Andriod client API: API Client SYS: system, usually because burst |
| > status | String | Order status `live`: New order `partial_fill`: Partially filled `filled`: Fully filled `cancelled`: The order is cancelled `reject`: Rejected |
| > side | String | Direction sell: Sell buy: Buy |
| > baseSize | String | Number in base coins |
| > quoteSize | String | Number in quote currency |
| > orderType | String | Order type limit market |
| > cTime | String | Creation time |
| > uTime | String | Updated time |
| > loanType | String | Margin order model normal: Normal order autoLoan: auto-borrow order autoRepay: auto-repay order autoLoanAndRepay: auto-borrow and auto-repay order |
| maxId | String | Max ID of current search result |
| minId | String | Min ID of current search result, use: `idLessThan=minId` in the next query |