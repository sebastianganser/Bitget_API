# Sub Deposit Records

Rate limit:10 req/sec/UID

### Description[​](#description "Direct link to Description")

Only applicable for ND broker main-account to get ND sub-accounts deposit record

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/broker/subaccount-deposit

Request Example

```json
curl "https://api.bitget.com/api/v2/broker/subaccount-deposit?startTime=1700561435000&endTime=1703153435933" \  
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
| orderId | String | No | recordsId   orderId and userId cannot both be empty. |
| userId | String | No | Sub account UID   orderId and userId cannot both be empty. |
| startTime | String | No | Start timestamp  Milliseconds format of timestamp Unix, e.g. 1597026383085 (The maximum time span supported is three months. The default end time is three months if no value is set for the end time. ) |
| endTime | String | No | End timestamp  Milliseconds format of timestamp Unix, e.g. 1597026383085 (The maximum time span supported is three months. The default start time is three months ago if no value is set for the start time. ) |
| limit | String | No | Number of queries: Default: 20, maximum: 100. |
| idLessThan | String | No | Separate page content before this ID is requested (older data), and the value input should be the end ID of the last request. |

Response Example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1689833233282,  
    "data": [{  
        "orderId": "XXXXX",  
        "txId": "XXXXXXX",  
        "coin": "USDT",  
        "type": "deposit",  
        "dest": "internal_transfer",  
        "amount": "10",  
        "status": "success",  
        "fromAddress": "123123",  
        "toAddress": "456456",  
        "fee": "1",  
        "chain": "erc20",  
        "confirm": "3",  
        "tag": "xx",  
        "userId": "123456",  
        "cTime": "1689833233282",  
        "uTime": "1689833233282"  
    }]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| orderId | String | orderId |
| txId | String | txId |
| coin | String | coin |
| type | String | type |
| dest | String | Deposit type |
| amount | String | Deposit amount |
| status | String | The status of the deposit process |
| fromAddress | String | Deposit initiator information. When recharging on the chain, this field is the initiator wallet address; when transferring internally, this field is UID |
| toAddress | String | Deposit recipient information. When recharging on the chain, this field is the initiator wallet address; when transferring internally, this field is UID |
| fee | String | The amount of the fee. The pricing unit is the recharge currency |
| chain | String | Deposit network |
| confirm | String | Confirm the number of blocks |
| tag | String | tag |
| userId | String | Sub-account ID |
| cTime | String | creation time ms |
| uTime | String | update time ms |