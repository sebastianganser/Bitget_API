# Get Tracking Order Summary

Rate Limit: 5 req/sec/UID

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/copy/mix-trader/order-total-detail

Request Example

```json
curl "https://api.bitget.com/api/v2/copy/mix-trader/order-total-detail" \  
  -H "ACCESS-KEY:your apiKey" \  
  -H "ACCESS-SIGN:*******" \  
  -H "ACCESS-PASSPHRASE:*****" \  
  -H "ACCESS-TIMESTAMP:1659076670000" \  
  -H "locale:en-US" \  
  -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

N/A

Response example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1695805917634,  
  "data": {  
    "roi": "19.38",  
    "tradingOrderNum": "105",  
    "totalFollowerNum": "134",  
    "currentFollowerNum": "4",  
    "totalpl": "$46.95",  
    "gainNum": "59",  
    "lossNum": "46",  
    "winRate": "56.123",  
    "tradingPairsAvailableList": [  
      "BTCUSDT"  
    ],  
    "lastWeekRoiList": [  
      {  
        "rate": "-14.130944",  
        "ctime": "1695139200000"  
      }  
    ],  
    "lastWeekProfitList": [],  
    "lastMonthRoiList": [  
      {  
        "rate": "-14.130944",  
        "ctime": "1693152000000"  
      }  
    ],  
    "totalEquity": "1776.03"  
  }  
}
```

### Response parameters[​](#response-parameters "Direct link to Response parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| roi | String | ROI |
| tradingOrderNum | String | Total opening orders |
| totalFollowerNum | String | Total followers |
| currentFollowerNum | String | Current number of followers |
| totalpl | String | Total profit (calculated in USD) |
| gainNum | String | Ratio of profitable trades |
| lossNum | String | Ratio of losing trades |
| totalEquity | String | Total assets |
| winRate | String | Win rate |
| tradingPairsAvailableList | List<String> | Available trading pairs |
| lastWeekRoiList | List | ROI in the last week |
| > rate | String | Rate of profit |
| > ctime | String | Time(timestamp) |
| lastWeekProfitList | List<Object> | Profit in the past week |
| > amount | String | Profit, USDT |
| > ctime | String | Time(timestamp) |
| lastMonthRoiList | List<Object> | ROI in the last month |
| > rate | String | Rate of profit |
| > ctime | String | Time(timestamp) |
| lastMonthProfitList | List<Object> | Profit in the last month |
| > amount | String | Profit, USDT |
| > ctime | String | Time(timestamp) |