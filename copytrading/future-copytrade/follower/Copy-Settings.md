# Copy settings

Rate Limit: 1 req/sec/UID

This interface is designed for setting up order following for the new version of followers. Currently, the interface only supports intelligent proportion and does not support multivariate exploration.

* Criteria for the new version of followers: Users who registered after January 26, 2024, or users who registered before January 26, 2024 and have manually upgraded.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* POST /api/v2/copy/mix-follower/copy-settings

Request

```json
curl "https://api.bitget.com/api/v2/copy/mix-follower/copy-settings" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*******" \  
  -H "ACCESS-PASSPHRASE:*****" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json" \  
  -d '{"traderId":"xxxxxxxxxxxx","copyAmount":"200"}'
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| traderId | String | Yes | ID of the elite trader that you followed |
| copyAmount | String | Yes | Copy trading amount, must be a positive integer not less than 50, denominated in USDT.. |
| copyAllPostions | String | No | Whether to follow all positions of the trader.  `yes`Follow all positions. `no` Do not follow all positions   If not provided, the default value is`no` |
| autoCopy | String | No | Whether to automatically follow new symbol opened by traders(only takes effect when mode is basic).  `on`Automatic following. `off`Not automatically following   If not provided, the default value is`on` |
| equityGuardian | String | No | Equity protection switch.  `on`Enabled   `off`Disabled   If not provided,the default value is`off` |
| equityGuardianMode | String | No | Equity protection mode, triggered when equityGuardian=on.   `amount`Fixed amount protection   `percentage`Percentage-based protection   If not provided, the default value is`amount` |
| equity | String | No | Equity protection trigger value. Required when equityGuardian=on. Must be a positive integer. If equityGuardian Mode=percentage, range is [1-100], representing 1%-100%. If equityGuardianMode=amount, it represents a fixeed loss amount. |
| marginMode | String | No | Margin mode.  `follow_trader`Follow the trader's leverage. `crossed_margin`Cross margin  `isolated_margin`Isolated margin.  If not provided, the default value is`follow_trader` |
| leverage | String | No | Leverage mode, effective when marginMode=follow\_trader.  `follow_trader`Follow trader.  `fixed_leverage`Use fixed leverage.   Default: follow\_trader. |
| multiple | String | No | Leverage multiple, ranging from [1,125]. Default: 10. |

Response

```json
{  
    "code": "00000",  
    "msg": "success",  
    "requestTime": 1695872676719,  
    "data": "success"  
}
```

### Response parameters[​](#response-parameters "Direct link to Response parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| data | String | `success` Success   `failure` Failure |