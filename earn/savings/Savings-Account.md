# Savings Account

Frequency limit: 10c/1s (Uid)

### Description[​](#description "Direct link to Description")

Get savings account info

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/earn/savings/account

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
    "requestTime": 1696748551073,  
    "data": {  
        "btcAmount": "0.35821314",  
        "usdtAmount": "9481.55500000",  
        "btc24hEarning": "0.00000009",  
        "usdt24hEarning": "0.00263912",  
        "btcTotalEarning": "0.00000761",  
        "usdtTotalEarning": "0.20145653"  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| btcAmount | String | Estimated total asset value in BTC |
| usdtAmount | String | Estimated total asset value in USDT |
| btc24hEarning | String | 24-hour earning in BTC |
| usdt24hEarning | String | 24-hour earning in USDT |
| btcTotalEarning | String | Cumulative earning in BTC |
| usdtTotalEarning | String | Cumulative earning in USDT |