# Upgrade Account

### Description[​](#description "Direct link to Description")

1. No account type restrictions; both parent and sub-accounts are supported.
2. This interface is only used for upgrading to the unified account mode.
3. Please note that as the account upgrade process takes approximately 1 minute, the successful response you receive only indicates that the request has been received, and does not mean that the account has been successfully upgraded to a unified account.
4. Please use the query upgrade status interface to confirm whether the account upgrade is successful.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/spot/account/upgrade
* Rate Limit: 1 req/sec/UID

Request Example

```json
curl -X POST "https://api.bitget.com/api/v2/spot/account/upgrade" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json" \  
   -d '{}'
```

### Request Parameter[​](#request-parameter "Direct link to Request Parameter")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| subUid | String | No | Sub-account User ID |

Response Example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1728625799912,  
  "data": null  
}
```

### Response Parameter[​](#response-parameter "Direct link to Response Parameter")

N/A