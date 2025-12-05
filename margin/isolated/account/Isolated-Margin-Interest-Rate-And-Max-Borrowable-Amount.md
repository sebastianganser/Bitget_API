# Get Isolated Interest Rate and Max Borrowable

Frequency limit:10 times/1s (UID)

### Description[​](#description "Direct link to Description")

This interface will determine the user's VIP level based on the User ID sending the request, and then return information such as interest rates and limits based on the VIP level.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v2/margin/isolated/interest-rate-and-limit

Request Example

```json
curl "https://api.bitget.com/api/v2/margin/isolated/interest-rate-and-limit?symbol=BTCUSDT"  -H "ACCESS-KEY:*******" \  
   -H "ACCESS-SIGN:*******" \  
   -H "ACCESS-PASSPHRASE:*****" \  
   -H "ACCESS-TIMESTAMP:1659076670000" \  
   -H "locale:en-US" \  
   -H "Content-Type: application/json"
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| symbol | String | Yes | Trading pairs, like BTCUSDT |

Response Example

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1694579779768,  
  "data": [  
    {  
      "symbol": "BTCUSDT",  
      "leverage": "5",  
      "baseCoin": "BTC",  
      "baseTransferable": true,  
      "baseBorrowable": true,  
      "baseDailyInterestRate": "0.00007113",  
      "baseAnnuallyInterestRate": "0.02596245",  
      "baseMaxBorrowableAmount": "0",  
      "baseVipList": [  
        {  
          "level": "0",  
          "dailyInterestRate": "0.00007333",  
          "limit": "0",  
          "annuallyInterestRate": "0.02676545",  
          "discountRate": "1"  
        }  
      ],  
      "quoteCoin": "USDT",  
      "quoteTransferable": true,  
      "quoteBorrowable": true,  
      "quoteDailyInterestRate": "0.00011963",  
      "quoteAnnuallyInterestRate": "0.04366495",  
      "quoteMaxBorrowableAmount": "0",  
      "quoteList": [  
        {  
          "level": "0",  
          "dailyInterestRate": "0.00012333",  
          "limit": "0",  
          "annuallyInterestRate": "0.04501545",  
          "discountRate": "1"  
        }  
      ]  
    }  
  ]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| symbol | String | Trading pair |
| baseCoin | String | Base currency |
| leverage | String | Leverage: default: 10 |
| baseTransferable | Boolean | Is the base currency transferable? true: Transferable false: Not transferable |
| baseBorrowable | Boolean | Whether or not the base currency can be borrowed? true: Borrowable false: Not borrowable |
| baseDailyInterestRate | String | Non-VIP daily interest rate of the base currency |
| baseAnnuallyInterestRate | String | Non-VIP APR of the base currency |
| baseMaxBorrowableAmount | String | Maximum borrow in base currency |
| baseVipList | Array | Base currency VIP |
| > level | String | VIP level |
| > limit | String | VIP limit |
| > dailyInterestRate | String | VIP daily interest rate |
| > annuallyInterestRate | String | VIP APR |
| > discountRate | String | VIP discount: 1 is for 100%, i.e. no discount; 0.97 is for 97% of the original rate |
| quoteCoin | String | Quote currency |
| quoteTransferInAble | Boolean | Whether the quote currency is transferable |
| quoteTransferable | Boolean | Whether the quote currency is borrowable |
| quoteBorrowable | String | Non-VIP daily interest rate of the quote currency |
| quoteAnnuallyInterestRate | String | Non-VIP APR of the quote currency |
| quoteMaxBorrowableAmount | String | Non-VIP maximum borrow in quote currency |
| quoteList | Array | Quote currency VIP |
| > level | String | VIP level |
| > limit | String | VIP limit |
| > dailyInterestRate | String | VIP daily interest rate |
| > annuallyInterestRate | String | VIP APR |
| > discountRate | String | VIP discount: 1 is for 100%, i.e. no discount; 0.97 is for 97% of the original rate |