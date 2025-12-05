# Sub Deposit Auto Transfer

Frequency limit:10 times/1s (User ID)

### Description[​](#description "Direct link to Description")

Only applicable for ND broker main-account

After call, the fund recharge to the given subaccount will automatically transfer to the specified 'toAccountType'

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/broker/account/set-subaccount-autotransfer

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/broker/account/set-subaccount-autotransfer" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*" \  
  -H "ACCESS-PASSPHRASE:*" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:zh-CN" \  
  -H "Content-Type: application/json" \  
  -d '{"subUid": "111111","coin": "USDT","toAccountType":"usdt-futures"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| subUid | String | Yes | Sub account UID |
| coin | String | Yes | Coin |
| toAccountType | String | Yes | To account type： spot default usdt-futures USDT professional futures（corresponding to mix\_usdt） coin-futures Mixed futures（corresponding to mix\_usd） usdc-futures USDC professional futures（corresponding to mix\_usdc） |

Response Example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1695786112492,  
    "data": "success"  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| data | String | 'success' or 'fail' |