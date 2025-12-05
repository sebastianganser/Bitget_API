# SharkFin Account

Frequency limit: 10c/1s (Uid)

### Description[​](#description "Direct link to Description")

Get sharkfin account info

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/earn/sharkfin/account

Request Example

```json
curl "https://api.bitget.com/api/v2/earn/savings/account" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*******" \  
  -H "ACCESS-PASSPHRASE:*****" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

N/A

Response Example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1696755312297,  
    "data": {  
        "btcSubscribeAmount": "0.00000000",  
        "usdtSubscribeAmount": "0.00",  
        "btcHistoricalAmount": "0.00000000",  
        "usdtHistoricalAmount": "0.00000000",  
        "btcTotalEarning": "0.00000000",  
        "usdtTotalEarning": "0.00000000"  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| btcSubscribeAmount | String | Estimated total asset value in BTC |
| usdtSubscribeAmount | String | Estimated total asset value in USDT |
| btcHistoricalAmount | String | 24-hour earning in BTC |
| usdtHistoricalAmount | String | 24-hour earning in USDT |
| btcTotalEarning | String | Cumulative earning in BTC |
| usdtTotalEarning | String | Cumulative earning in USDT |