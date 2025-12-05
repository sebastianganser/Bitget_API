# Create Subaccount Deposit Address

Frequency limit:10 times/1s (User ID)

### Description[​](#description "Direct link to Description")

Only applicable for ND broker main-account

Create deposit address for the specified subaccount

So far the `coin` in request parameter only accepts the following coins:  
BTC,ETH,USDT,USDC,TRX,XRP,LTC,SOL,BNB,FTM,DOGE,ADA,SHIB,UNI,SEI,SUI,POL,FIL,LINK,TON,ARB,OP,DOT,AVAX

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/broker/account/subaccount-address

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/broker/account/subaccount-address" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*" \  
  -H "ACCESS-PASSPHRASE:*" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:zh-CN" \  
  -H "Content-Type: application/json" \  
  -d '{"subUid":"111111","coin":"ETH"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| subUid | String | Yes | Sub account UID |
| coin | String | Yes | Coin, e.g: BTC |
| chain | String | No | Chain name, default will use the main-chain of the 'coin' |

Response Example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1695785563368,  
    "data": {  
        "subUid": "*************",  
        "coin": "ETH",  
        "address": "0x1eae2xxxxxxx7360bc59d2axxxxxx0caec9e",  
        "chain": "trc20",  
        "tag": "address1",  
        "url": "https://etherscan.io/tx/",  
        "cTime": "1694966400000"  
    }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| subUid | String | Sub account UID |
| address | String | Deposit address |
| chain | String | Chain name |
| coin | String | Coin, like USDT |
| tag | String | Tag value, i.e. 'memo' of 'EOS', 'comment' of 'TON' |
| url | String | Block chain address |
| ctime | String | Created Time, ms |