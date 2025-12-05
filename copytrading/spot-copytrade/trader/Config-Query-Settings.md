# Get Copytrade Configuration

Rate Limit: 5 req/sec/UID

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/copy/spot-trader/config-query-settings

Request Example

```json
curl "https://api.bitget.com/api/v2/copy/spot-trader/config-query-settings" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*******" \  
  -H "ACCESS-PASSPHRASE:*****" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json"
```

### Request Parameter[​](#request-parameter "Direct link to Request Parameter")

N/A

Response example

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1695807020372,  
    "data": {  
        "removeLimitUsdt": "100",  
        "spotInfoList": [  
            {  
                "maxQuoteSize": "5000000",  
                "surplusQuoteSize": "4998894.59",  
                "symbol": "BTCUSDT"  
            },  
            {  
                "maxQuoteSize": "300000",  
                "surplusQuoteSize": "300000",  
                "symbol": "ETHBTC"  
            },  
            {  
                "maxQuoteSize": "50000",  
                "surplusQuoteSize": "50000",  
                "symbol": "ETHUSDT"  
            }  
        ],  
        "labelList": [],  
        "enable": "YES",  
        "showAssetsMap": "NO",  
        "showEquity": "NO",  
        "traceSymbolList": [  
            {  
                "enable": "NO",  
                "symbol": "BGBUSDT",  
                "minOpenCount": "0.0001"  
            },  
            {  
                "enable": "YES",  
                "symbol": "BTCUSDT",  
                "minOpenCount": "0.0005"  
            },  
            {  
                "enable": "YES",  
                "symbol": "ETHBTC",  
                "minOpenCount": "0.0001"  
            },  
            {  
                "enable": "YES",  
                "symbol": "ETHUSDT",  
                "minOpenCount": "0.0001"  
            }  
        ]  
    }  
}
```

### Response Description[​](#response-description "Direct link to Response Description")

| Parameter | Parameter Type | Description |
| --- | --- | --- |
| removeLimitUsdt | String | The maximum limit of follower assets can be removed. (followers with the assets less than this value can be removed) |
| spotInfoList | List | Overview of elite trade amount |
| >maxQuoteSize | String | Maximum single order amount (price currency) |
| >surplusQuoteSize | String | Remaining amount (price currency) |
| >symbol | String | symbol |
| labelList | List | Tag overview |
| >id | String | tag id |
| >name | String | tag name |
| enable | String | Activate elite trading or not? yes: on; no: off |
| showAssetsMap | String | Display composition of assets or not? yes: on; no: off |
| showEquity | String | Display total funds or not? yes: on; no: off |
| traceSymbolList | List | Overview of trading pairs for elite trades |
| >enable | String | Is this trading pair open for elite trades? yes: on; no: off |
| >symbol | String | Trading pair |
| >minOpenCount | String | Minimum number of elite trades for elite traders |