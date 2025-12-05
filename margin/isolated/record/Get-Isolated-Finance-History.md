# Get Isolated Financial History

Frequency limit: 10 times/1s (UID)

### Description[​](#description "Direct link to Description")

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/margin/isolated/financial-records

Request Example

```json
curl "https://api.bitget.com/api/v2/margin/isolated/financial-records?symbol=BTCUSDT&startTime=1692690126000"  -H "ACCESS-KEY:*******" \  
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
| marginType | String | No | Capital flow type transfer\_in: inbound transfer transfer\_out: outbound transfer borrow: Borrowings repay: Repayment liquidation\_fee: Liquidation fee compensate: Risk fund compensation for collateral shortfall deal\_in: buy deal\_out: sell confiscated: Deducted for collateral shortfall exchange\_in: Exchange income, charged to the system account exchange\_out: Exchange spending, received by the system account sys\_exchange\_in: exchange income of the system account, with exchange spending appearing at the same time sys\_exchange\_out: exchange spending of the system account, with exchange income appearing at the same time |
| coin | String | No | Coin |
| startTime | String | Yes | Start time, Unix millisecond timestamps |
| endTime | String | No | End time, Unix millisecond timestamps Maximum interval between start and end times is 90 days |
| limit | String | No | Number of queries Default: 100, maximum: 500 |
| idLessThan | String | No | For turning pages. No setting is needed when querying for the first time. Set to to smallest marginId returned from the last query when searching for data in the second page and other paged. Data smaller than the marginId entered will be returned. This is designed to shorten the query response time. |

Response Example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1695625219083,  
    "data": {  
        "resultList": [  
            {  
                "coin": "BTC",  
                "symbol": "BTCUSDT",  
                "marginId": "1",  
                "amount": "-1",  
                "balance": "199999.0036963",  
                "fee": "0",  
                "marginType": "repay",  
                "cTime": "1695624616058",  
                "uTime": "1695624616058"  
            }  
        ],  
        "maxId": "1",  
        "minId": "1"  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| resultList | List | List |
| > symbol | String | Trading pair |
| > coin | String | Coin |
| > marginId | String | Capital flow ID |
| > marginType | String | Capital flow type transfer\_in: assets transferred in transfer\_out: assets transferred out borrow: borrow Repay: repay liquidation\_fee: liquidation fee compensate: collateral shortfall compensation from risk fund deal\_in: trade and deposit (buy) deal\_out: trade and withdraw (sell) confiscated: deduction for collateral shortfall exchange\_in: exchange income, charged from the system account exchange\_out: exchange expense, charged to the system account sys\_exchange\_in: exchange income of the system account, with exchange expense appearing at the same time sys\_exchange\_out: exchange expense of the system account, with exchange income appearing at the same time |
| > amount | String | Capital flow amount |
| > balance | String | Account balance |
| > fee | String | Transaction fee details |
| > cTime | String | Creation time, millisecond timestamp |
| > uTime | String | Update time, millisecond timestamp |
| maxId | String | Max ID of current search result |
| minId | String | Min ID of current search result, use: `idLessThan=minId` in the next query |