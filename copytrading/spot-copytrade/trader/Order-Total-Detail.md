# Get Data Indicator Statistics

Rate Limit: 5 req/sec/UID

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/copy/spot-trader/order-total-detail

Request Example

```json
curl "https://api.bitget.com/api/v2/copy/spot-trader/order-total-detail" \  
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
    "requestTime": 1695806393920,  
    "data": {  
        "totalFollowerNum": "1",  
        "currentFollowerNum": "1",  
        "maxFollowerNum": "300",  
        "tradingOrderNum": "20",  
        "totalpl": "180.81650415",  
        "gainNum": "9",  
        "lossNum": "11",  
        "totalEquity": "1002283.204381698640000000",  
        "winRate": "10.00",  
        "lastWeekRoiList": [  
            {  
                "rate": "14.08",  
                "ctime": "1695139200000"  
            },  
            {  
                "rate": "14.08",  
                "ctime": "1695225600000"  
            },  
            {  
                "rate": "16.84",  
                "ctime": "1695312000000"  
            },  
            {  
                "rate": "16.84",  
                "ctime": "1695398400000"  
            },  
            {  
                "rate": "16.84",  
                "ctime": "1695484800000"  
            },  
            {  
                "rate": "16.84",  
                "ctime": "1695571200000"  
            },  
            {  
                "rate": "16.84",  
                "ctime": "1695657600000"  
            },  
            {  
                "rate": "16.84",  
                "ctime": "1695744000000"  
            }  
        ],  
        "lastMonthRoiList": [  
            {  
                "rate": "0",  
                "ctime": "1693152000000"  
            },  
            {  
                "rate": "0",  
                "ctime": "1693238400000"  
            },  
            {  
                "rate": "0",  
                "ctime": "1693324800000"  
            },  
            {  
                "rate": "-0.06",  
                "ctime": "1693411200000"  
            },  
            {  
                "rate": "14.14",  
                "ctime": "1693497600000"  
            },  
            {  
                "rate": "14.14",  
                "ctime": "1693584000000"  
            },  
            {  
                "rate": "14.14",  
                "ctime": "1693670400000"  
            },  
            {  
                "rate": "14.08",  
                "ctime": "1693756800000"  
            },  
            {  
                "rate": "14.08",  
                "ctime": "1693843200000"  
            },  
            {  
                "rate": "14.08",  
                "ctime": "1693929600000"  
            },  
            {  
                "rate": "14.08",  
                "ctime": "1694016000000"  
            },  
            {  
                "rate": "14.08",  
                "ctime": "1694102400000"  
            },  
            {  
                "rate": "14.08",  
                "ctime": "1694188800000"  
            },  
            {  
                "rate": "14.08",  
                "ctime": "1694275200000"  
            },  
            {  
                "rate": "14.08",  
                "ctime": "1694361600000"  
            },  
            {  
                "rate": "14.08",  
                "ctime": "1694448000000"  
            },  
            {  
                "rate": "14.08",  
                "ctime": "1694534400000"  
            },  
            {  
                "rate": "14.08",  
                "ctime": "1694620800000"  
            },  
            {  
                "rate": "14.08",  
                "ctime": "1694707200000"  
            },  
            {  
                "rate": "14.08",  
                "ctime": "1694793600000"  
            },  
            {  
                "rate": "14.08",  
                "ctime": "1694880000000"  
            },  
            {  
                "rate": "14.08",  
                "ctime": "1694966400000"  
            },  
            {  
                "rate": "14.08",  
                "ctime": "1695052800000"  
            },  
            {  
                "rate": "14.08",  
                "ctime": "1695139200000"  
            },  
            {  
                "rate": "14.08",  
                "ctime": "1695225600000"  
            },  
            {  
                "rate": "16.84",  
                "ctime": "1695312000000"  
            },  
            {  
                "rate": "16.84",  
                "ctime": "1695398400000"  
            },  
            {  
                "rate": "16.84",  
                "ctime": "1695484800000"  
            },  
            {  
                "rate": "16.84",  
                "ctime": "1695571200000"  
            },  
            {  
                "rate": "16.84",  
                "ctime": "1695657600000"  
            },  
            {  
                "rate": "16.84",  
                "ctime": "1695744000000"  
            }  
        ],  
        "lastWeekProfitList": [  
            {  
                "amount": "156.403443",  
                "ctime": "1695139200000"  
            },  
            {  
                "amount": "156.403443",  
                "ctime": "1695225600000"  
            },  
            {  
                "amount": "187.067143",  
                "ctime": "1695312000000"  
            },  
            {  
                "amount": "187.067143",  
                "ctime": "1695398400000"  
            },  
            {  
                "amount": "187.067143",  
                "ctime": "1695484800000"  
            },  
            {  
                "amount": "187.067143",  
                "ctime": "1695571200000"  
            },  
            {  
                "amount": "180.816504",  
                "ctime": "1695657600000"  
            },  
            {  
                "amount": "180.816504",  
                "ctime": "1695744000000"  
            }  
        ],  
        "lastMonthProfitList": [  
            {  
                "amount": "-0.703906",  
                "ctime": "1695139200000"  
            },  
            {  
                "amount": "-0.703906",  
                "ctime": "1695225600000"  
            },  
            {  
                "amount": "187.067143",  
                "ctime": "1695312000000"  
            },  
            {  
                "amount": "187.067143",  
                "ctime": "1695398400000"  
            },  
            {  
                "amount": "187.067143",  
                "ctime": "1695484800000"  
            },  
            {  
                "amount": "187.067143",  
                "ctime": "1695571200000"  
            },  
            {  
                "amount": "180.816504",  
                "ctime": "1695657600000"  
            },  
            {  
                "amount": "180.816504",  
                "ctime": "1695744000000"  
            }  
        ]  
    }  
}
```

### Response Description[​](#response-description "Direct link to Response Description")

| Parameter | Parameter Type | Description |
| --- | --- | --- |
| totalFollowerNum | String | Total followers |
| currentFollowerNum | String | Current number of followers |
| maxFollowerNum | String | Maximum number of followers for the elite trader |
| tradingOrderNum | String | Total opening orders |
| totalpl | String | Total profit (USDT) |
| gainNum | String | Ratio of profitable trades |
| lossNum | String | Ratio of losing trades |
| totalEquity | String | Total assets |
| winRate | String | Win rate |
| lastWeekRoiList | List | ROI for the last week |
| > rate | String | rate |
| > ctime | String | time |
| lastMonthRoiList | List | 30-day ROI |
| > rate | String | rate |
| > ctime | String | time |
| lastWeekProfitList | List | Profit for the last week |
| > amount | String | amount, USDT |
| > ctime | String | time |
| lastMonthProfitList | List | 30-day Profit |
| > amount | String | amount, USDT |
| > ctime | String | time |