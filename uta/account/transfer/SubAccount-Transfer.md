# Main-Sub Account Transfer

### Description[​](#description "Direct link to Description")

Sub-account to Main Account Asset Transfer. The transfer types supported by this API include:

* Main account to sub-account (only the main account API Key has permission)
* Sub-account to main account (only the main account API Key has permission)
* Sub-account to sub-account (only the main account API Key has permission, and the sending and receiving sub-accounts must belong to the same main account)
* Sub-account internal transfer (only the main account API Key has permission, and the sending and receiving sub-accounts must be the same sub-account)

The UID of the transferring and receiving accounts in the request parameters must be in a main-sub or sibling
relationship, and the caller must be the main account API Key.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v3/account/sub-transfer
* Rate limit: 5/sec/UID
* Unified account management read and write permissions are required
* Only the main account can call this API

Request

```json
curl -X POST "https://api.bitget.com/api/v3/account/sub-transfer" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json" \  
   -d '{"fromType":"spot","toType":"uta","amount":"1000","coin":"USDT","fromUserId":"1991021336","toUserId":"4746345901","clientOid":"xxxxx"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| fromType | String | Yes | Transferring Account Type `spot` Spot account/Funding account `p2p` P2P account/OTC account `usdt_futures` USDT-Margined Futures Account `coin_futures` Coin-Margined Futures Account `usdc_futures` USDC Futures Account `crossed_margin` Cross Margin Account `uta` Unified Account  **The above enumerations apply to the main account**  If it is a sub-account: Unified account sub-account only supports `uta` and `spot` Classic account sub-account does not support `uta` and `p2p` |
| toType | String | Yes | Receiving Account Type `spot` Spot account/Funding account `p2p` P2P account/OTC account `usdt_futures` USDT-Margined Futures Account `coin_futures` Coin-Margined Futures Account `usdc_futures` USDC Futures Account `crossed_margin` Cross Margin Account `uta` Unified Account  **The above enumerations apply to the main account**  If it is a sub-account: Unified account sub-account only supports `uta` and `spot` Classic account sub-account does not support `uta` and `p2p` |
| amount | String | Yes | Amount to Transfer In |
| coin | String | Yes | Transfer Currency, e.g., BTC |
| fromUserId | String | Yes | Transferring Account UID |
| toUserId | String | Yes | Receiving Account UID |
| clientOid | String | Yes | clientOid,Cannot exceed 64 characters. |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1740213448866,  
  "data": {  
    "transferId": "172947298237423",  
    "clientOid": "test_001"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| transferId | String | transferId |
| clientOid | String | clientOid |