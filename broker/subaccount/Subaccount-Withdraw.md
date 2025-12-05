# Subaccount Withdrawal

Rate Limit: 1 req/sec/UID

### Description[​](#description "Direct link to Description")

ND broker initiates on chain withdraw or internal withdraw.

Only applicable for ND broker main-account

So far the `coin` in request parameter only accepts the following coins:  
BTC,ETH,USDT,USDC,TRX,XRP,LTC,SOL,BNB,FTM,DOGE,ADA,SHIB,UNI,SEI,SUI,POL,FIL,LINK,TON,ARB,OP,DOT,AVAX

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/broker/account/subaccount-withdrawal

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/broker/account/subaccount-withdrawal" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*" \  
  -H "ACCESS-PASSPHRASE:*" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:zh-CN" \  
  -H "Content-Type: application/json" \  
  -d ' {"subUid":"11111","dest":"on_chain","coin": "ETH","address": "0x1eae2eb9f62dxxxxxxxxxx86a50caec9e","amount": "0.1","remark": "sub to sub"}
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| subUid | String | Yes | Sub account UID |
| coin | String | Yes | Coin, e.g. BTC Only accept BTC/ETH/USDT/USDC/TRX/XRP/LTC/SOL/BNB/FTM/DOGE/ADA/SHIB/UNI/SEI/SUI/POL/FIL/LINK/TON/ARB/OP/DOT/AVAX |
| dest | String | Yes | Withdraw type.  `on_chain`: on chain withdraw `internal_transfer`: internal withdraw |
| chain | String | No | Chain name It will use the main-chain of the 'coin' by default |
| address | String | Yes | Address When `dest`==`on_chain`, it should be the chain address When `dest`==`internal_transfer`, it should be UID |
| amount | String | Yes | Withdraw amount |
| tag | String | No | Tag value for on chain withdraw, i.e. 'memo' of 'EOS', 'comment' of 'TON' |
| clientOid | String | No | Client Order ID |

Response Example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1695785738672,  
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
| clientOid | String | Client Order ID |