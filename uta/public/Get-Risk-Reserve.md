# Get Risk Reserve

### Description[​](#description "Direct link to Description")

Query risk reserve records.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/market/risk-reserve
* Rate limit: 20/sec/IP

Request

```json
curl "https://api.bitget.com/api/v3/market/risk-reserve?category=USDT-FUTURES&symbol=BTCUSDT"  \
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| category | String | Yes | Product type `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures |
| symbol | String | Yes | Symbol name  e.g.,`BTCUSDT` |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1753793743942,  
  "data": {  
    "totalBalance": "",  
    "coin": "USDT",  
    "riskReserveRecords": [  
      {  
        "type": "",  
        "amount": "9.8470265278770000",  
        "balance": "95815.6773460800020000",  
        "ts": "1753718400000"  
      },  
      {  
        "type": "",  
        "amount": "0.4328615782800000",  
        "balance": "95805.8303195521250000",  
        "ts": "1753632000000"  
      }  
    ]  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| totalBalance | String | Total balance of the risk reserve fund （Deprecated） |
| coin | String | Settlement coin |
| riskReserveRecords | String | Risk reserve records |
| >type | String | Operation type （Deprecated） |
| >amount | String | Fund adjustment amount |
| >balance | String | The balance of the risk reserve fund |
| >ts | String | The timestamp that the system records the data  A Unix timestamp in milliseconds |