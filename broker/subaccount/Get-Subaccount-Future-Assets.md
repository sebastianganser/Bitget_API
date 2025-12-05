# Get Subaccount Future Assets

Frequency limit:10 times/1s (User ID)

### Description[​](#description "Direct link to Description")

Only applicable for ND broker main-account

Fetch the future assets of the given subaccount

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/broker/account/subaccount-future-assets

Request Example

```json
curl "https://api.bitget.com/api/v2/broker/account/subaccount-future-assets?productType=usdt-futures&subUid=111111" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*" \  
  -H "ACCESS-PASSPHRASE:*" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:zh-CN" \  
  -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| subUid | String | Yes | Sub account UID |
| productType | String | Yes | Product type `USDT-FUTURES` USDT-M Futures `COIN-FUTURES` Coin-M Futures `USDC-FUTURES` USDC-M Futures |

Response Example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1695785239709,  
    "data": {  
        "assetsList": [{  
                "marginCoin": "USDT",  
                "available": "0.00000000",  
                "frozen": "0.00000000",  
                "locked": "0.00000000",  
                "crossedMaxAvailable": "0.00000000",  
                "isolatedMaxAvailable": "0.00000000",  
                "maxTransferOut": "0.00000000",  
                "accountEquity": "0.00000000",  
                "usdtEquity": "0.00000000",  
                "btcEquity": "0.00000000",  
                "unrealizedPL": "0.00000000",  
                "uTime": "1695024539000"  
            }  
        ]  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| assetsList | List<Object> | Asset list |
| marginCoin | String | Margin coin |
| locked | String | Locked amount (margin currency) |
| available | String | Available balance |
| crossedMaxAvailable | String | The maximum available balance for the 'crossed' Margin Mode (margin currency) |
| isolatedMaxAvailable | String | The maximum available balance for the 'isolated' Margin Mode(margin currency) |
| maxTransferOut | String | Maximum transferable |
| accountEquity | String | Account equity (margin currency) |
| usdtEquity | String | Account equity in USDT |
| btcEquity | String | Account equity in BTC |
| unrealizedPL | String | Unrealized PnL |
| uTime | String | Updated time, ms |