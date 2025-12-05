# Get the transfer records of Main-Sub account

### Description[​](#description "Direct link to Description")

This API supports retrieving transfer records between main and sub accounts.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/account/sub-transfer-record
* Rate limit: 5/sec/UID
* Unified account management read permissions are required

Request

```json
curl -X GET "https://api.bitget.com/api/v3/account/sub-transfer-record?limit=100" \  
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
| subUid | String | No | Sub-account UID. If not provided, transfer records of the main account will be retrieved. |
| role | String | No | Transfer-out account type `initiator` Initiator of the transfer `receiver` Recipient of the transfer Default: `initiator` |
| coin | String | No | Coin name |
| startTime | String | No | Start time for querying transfer records  * Unix millisecond timestamp, e.g., 1690196141868 * The time interval between startTime and endTime should not exceed 90 days. |
| endTime | String | No | End time for querying transfer records  * Unix millisecond timestamp, e.g., 1690196141868 * The time interval between startTime and endTime should not exceed 90 days. |
| clientOid | String | No | clientOid,Cannot exceed 64 characters. |
| limit | String | No | Items per page  The default value is 100, and the maximum value is 100. |
| cursor | String | No | Cursor ID Used for pagination. Do not pass it for the first query. For subsequent queries (second page and beyond), use the cursor returned from the previous query. |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1751453670468,  
  "data": {  
    "list": [  
      {  
        "transferId": "1320888751047921664",  
        "fromType": "spot",  
        "toType": "uta",  
        "amount": "20.00000000",  
        "coin": "USDT",  
        "fromUserId": "6841950428",  
        "toUserId": "6841950428",  
        "status": "Successful",  
        "clientOid": "1320888751047921664",  
        "createdTime": "1750650339853",  
        "updatedTime": "1750650339853",  
        "oldTransferId": "182797214"  
      },  
      {  
        "transferId": "1314821589514407936",  
        "fromType": "spot",  
        "toType": "isolated_margin",  
        "amount": "1.00000000",  
        "coin": "USDT",  
        "fromUserId": "6841950428",  
        "toUserId": "6841950428",  
        "status": "Successful",  
        "clientOid": "1314821589514407936",  
        "createdTime": "1749203815821",  
        "updatedTime": "1749203815821",  
        "oldTransferId": "175609331"  
      }  
    ],  
    "cursor": "2"  
  }  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Comments |
| --- | --- | --- |
| cursor | String | Cursor ID |
| list | Array | Transfer record List |
| transferId | String | TransferId |
| > fromType | String | Transferring Account Type `spot` Spot account/Funding Account `p2p` P2P account/OTC account `usdt_futures` USDT-Margined Futures Account `coin_futures` Coin-Margined Futures Account `usdc_futures` USDC Futures Account `crossed_margin` Cross Margin Account `unified` Unified Account |
| > toType | String | Receiving Account Type `spot` Spot account/Funding Account `p2p` P2P account/OTC account `usdt_futures` USDT-Margined Futures Account `coin_futures` Coin-Margined Futures Account `usdc_futures` USDC Futures Account `crossed_margin` Cross Margin Account `unified` Unified Account |
| > amount | String | Amount to Transfer In |
| > coin | String | Transfer Currency, e.g., BTC |
| > fromUserId | String | Transferring Account UID |
| > toUserId | String | Receiving Account UID |
| > status | String | Transfer status `Successful` Success `Failed` Failure `Processing` In progress |
| > clientOid | String | Custom ID |
| > oldTransferId | String | Old Transfer ID |
| > createdTime | String | Transfer creation time, Unix millisecond timestamp |
| > updatedTime | String | Transfer update time, Unix millisecond timestamp |