# Get Deposit Records

### Description[​](#description "Direct link to Description")

Get deposit records

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/account/deposit-records
* Rate limit: 10/sec/UID
* Permission: UTA mgt. (read)

Request

```json
curl "https://api.bitget.com/api/v3/account/deposit-records?startTime=1700561435000&endTime=1703153435933" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| coin | String | No | Coin name  - If left blank, all currency deposit records will be retrieved. |
| orderId | String | NO | Order ID  - Used for specifying order queries. |
| startTime | String | Yes | Query record start time  * Unix millisecond timestamp, e.g., 1690196141868 |
| endTime | String | Yes | Query record end time  * Unix millisecond timestamp, e.g., 1690196141868 |
| limit | String | No | Items per page  The default value is 20, and the maximum value is 100. |
| cursor | String | No | Cursor ID - Used for pagination to reduce query response time  - Do not send for the initial query. When querying the second page and subsequent data, use the smallest orderId returned from the previous query. The results will return data less than that value |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1740481864545,  
  "data": [  
      {  
        "orderId": "1278112570963742720",  
        "recordId": "1278112570963742720",  
        "coin": "usdt",  
        "type": "deposit",  
        "dest": "internal_transfer",  
        "size": "1",  
        "status": "success",  
        "fromAddress": "0x51xxx",  
        "toAddress": "0x51xxx",  
        "chain": "erc20",  
        "createdTime": "1740451703778",  
        "updatedTime": "1740451703778"  
      }  
  ]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| orderId | String | Order ID |
| recordId | String | Deposit Record ID - If `dest` is `on_chain`, it's the on-chain hash value - If `dest` is `internal_transfer`, it's the order ID |
| coin | String | Coin Name |
| type | String | Operation Type `deposit`Deposit |
| dest | String | Deposit Type `on_chain`On-chain deposit `internal_transfer`Internal transfer |
| size | String | Deposit Quantity |
| status | String | Deposit Status `pending`Pending `success`Success `fail`Fail |
| fromAddress | String | Deposit Initiator  - If `dest` is `on_chain`, it's the on-chain address. - If `dest` is `internal_transfer`, it's the UID, email, or mobile number. |
| toAddress | String | Deposit Recipient  - If `dest` is `on_chain`, it's the on-chain address. - If `dest` is `internal_transfer`, it's the UID, email, or mobile number. |
| chain | String | Deposit Network  - This parameter can be ignored when `dest` is `internal_transfer` |
| createdTime | String | Deposit record creation time, Unix millisecond timestamp |
| updatedTime | String | Deposit record update time, Unix millisecond timestamp |