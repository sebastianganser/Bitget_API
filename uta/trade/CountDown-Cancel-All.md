# CountDown Cancel All

### Description[​](#description "Direct link to Description")

In practical use, clients need to periodically send heartbeat requests to prevent uncontrolled open orders due to
abnormal disconnections or system crashes.  
For example, if your expected heartbeat interval is 10 seconds, meaning if no heartbeat request is sent for over 10
seconds, all orders must be canceled:

* Under normal circumstances, you can call this interface every 3-5 seconds, set the countdown to 10, and repeatedly
  call it to reset the countdown.
* Under abnormal circumstances, if no heartbeat request is sent for over 10 seconds, all orders under the account will
  be automatically canceled; after automatic cancellation, the Deadman Switch mechanism will automatically close.
* To manually close the Deadman Switch mechanism, simply set the countdown to 0.  
  P.S. This interface only supports canceling orders under UTA accounts, not classic accounts.

Please contact your dedicated Business Development representative to apply for access to this interface.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v3/trade/countdown-cancel-all
* Rate limit: 1/sec/UID
* Permission: UTA trade (read & write)

Request

```json
curl -X POST "https://api.bitget.com/api/v3/trade/countdown-cancel-all" \  
   -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*" \  
   -H "ACCESS-PASSPHRASE:*" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json" \  
   -d '{"countdown":"40"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Comments |
| --- | --- | --- | --- |
| countdown | String | Yes | Reconnect Window  - Unit: seconds  - Positive integer, range: [5, 60]. The minimum countdown is 5 second, and the maximum is 60 seconds. Filling in 0 cancels the countdown order cancellation function. |

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1728625799912,  
  "data": "success"  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

N/A