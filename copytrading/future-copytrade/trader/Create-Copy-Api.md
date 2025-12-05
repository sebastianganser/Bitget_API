# Create Copy ApiKey

Rate Limit: 1 req/sec/UID

This interface is used for the new version of Copy Traders to create a Copy API Key, which is of HMAC type. Old version Copy Traders will receive an error message "This interface is only applicable to the new Copy model" when calling the interface.

* The new version of Copy Traders have user identifiers on the following side. These traders support selecting both [Futures Trading] and [Copy Trading] when engaging in contract transactions.
* The Copy Trading API Key can only be created once. If a user attempts to create another one while already having a Copy API Key, an error will be returned stating "You have already created a Copy API Key."
* For elite traders, please strictly adhere to the list of trading pairs specified in the [Available trading pairs and parameters for elite traders](https://www.bitget.com/zh-CN/support/articles/12560603808895) when placing orders using the Copy Trading API Key. Trading pairs outside the announced list are not available for copy trading.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/copy/mix-trader/create-copy-api

Request

```json
curl "https://api.bitget.com/api/v2/copy/mix-trader/create-copy-api" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*******" \  
  -H "ACCESS-PASSPHRASE:*****" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json" \  
  -d '{"passphrase":"xxxxxxxxxxxxx"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| passphrase | String | Yes | Password length must be 8 to 32 characters, consisting of English letters and numbers. |

Response

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1695872676719,  
    "data": [  
        {  
            "apikey": "bg_xxxxxxxxxxxxxxxxxxxx",  
            "secret": "**********",  
            "permissions": ["copytrading_trade","contract_trade"]  
        }  
    ]  
}
```

### Response parameters[​](#response-parameters "Direct link to Response parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| apikey | String | API Key. |
| secret | String | API Secret. |
| permissions | String | API Key permissions:  `contract_trade`Contract trade. `copytrading_trade`Copy trade |