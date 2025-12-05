# Get Instruments

### Description[​](#description "Direct link to Description")

Query the specifications for online trading pair instruments.

### HTTP Request[​](#http-request "Direct link to HTTP Request")

* GET /api/v3/market/instruments
* Rate limit: 20/sec/IP

Request

```json
curl "https://api.bitget.com/api/v3/market/instruments?category=USDT-FUTURES"  \
```

### Request Parameters[​](#request-parameters "Direct link to Request Parameters")

| Parameters | Type | Required | Description |
| --- | --- | --- | --- |
| category | String | Yes | Product type   `SPOT` Spot trading   `MARGIN` Margin trading   `USDT-FUTURES` USDT futures   `COIN-FUTURES` Coin-M futures   `USDC-FUTURES` USDC futures |
| symbol | String | No | Symbol name  e.g.,`BTCUSDT` |

* Spot
* Futures
* Margin

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1734766810918,  
  "data": [  
    {  
      "symbol": "BTCUSDT",  
      "category": "SPOT",  
      "baseCoin": "BTC",  
      "quoteCoin": "USDT",  
      "buyLimitPriceRatio": "0.05",  
      "sellLimitPriceRatio": "0.05",  
      "feeRateUpRatio": "",  
      "minOrderQty": "0.00001",  
      "maxOrderQty": "",  
      "pricePrecision": "2",  
      "quantityPrecision": "6",  
      "quotePrecision": "6",  
      "minOrderAmount": "1",  
      "maxSymbolOrderNum": "",  
      "maxProductOrderNum": "",  
      "status": "online",  
      "offTime": "",  
      "limitOpenTime": "",  
      "maintainTime": "",  
      "areaSymbol": "no"  
    }  
  ]  
}
```

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1731056538962,  
  "data": [  
    {  
      "symbol": "BTCUSDT",  
      "category": "USDT-FUTURES",  
      "isRwa": "NO",  
      "baseCoin": "BTC",  
      "quoteCoin": "USDT",  
      "buyLimitPriceRatio": "1000",  
      "sellLimitPriceRatio": "1",  
      "feeRateUpRatio": "0.1",  
      "makerFeeRate": "0.0004",  
      "takerFeeRate": "0.0006",  
      "openCostUpRatio": "0.1",  
      "minOrderQty": "0.0001",  
      "maxOrderQty": "",  
      "pricePrecision": "1",  
      "quantityPrecision": "4",  
      "quotePrecision": "",  
      "priceMultiplier": "0.1",  
      "quantityMultiplier": "0.0001",  
      "symbolType": "perpetual",  
      "minOrderAmount": "2",  
      "maxSymbolOrderNum": "10000000",  
      "maxProductOrderNum": "10000000",  
      "maxPositionNum": "50",  
      "status": "online",  
      "offTime": "-1",  
      "limitOpenTime": "-1",  
      "deliveryTime": "",  
      "deliveryStartTime": "",  
      "deliveryPeriod": "",  
      "launchTime": "",  
      "fundInterval": "8",  
      "minLeverage": "1",  
      "maxLeverage": "125",  
      "maintainTime": "",  
      "maxMarketOrderQty": "220"  
    }  
  ]  
}
```

Response

```json
{  
  "code": "00000",  
  "msg": "success",  
  "requestTime": 1731056538962,  
  "data": [  
    {  
      "symbol": "ADAUSDT",  
      "category": "MARGIN",  
      "baseCoin": "ADA",  
      "quoteCoin": "USDT",  
      "buyLimitPriceRatio": "0.5",  
      "sellLimitPriceRatio": "0.5",  
      "feeRateUpRatio": "",  
      "minOrderQty": "0.001",  
      "maxOrderQty": "10000000000",  
      "pricePrecision": "3",  
      "quantityPrecision": "3",  
      "quotePrecision": "6",  
      "minOrderAmount": "5",  
      "maxSymbolOrderNum": "",  
      "maxProductOrderNum": "",  
      "maxPositionNum": "",  
      "status": "online",  
      "offTime": "",  
      "limitOpenTime": "",  
      "maintainTime": "",  
      "isIsolatedBaseBorrowable": "NO",  
      "isIsolatedQuotedBorrowable": "NO",  
      "warningRiskRatio": "0.8",  
      "liquidationRiskRatio": "1",  
      "maxCrossedLeverage": "3",  
      "maxIsolatedLeverage": "10",  
      "userMinBorrow": "0.00000001",  
      "areaSymbol": ""  
    }  
  ]  
}
```

### Response Parameters[​](#response-parameters "Direct link to Response Parameters")

| Parameters | Type | Description |
| --- | --- | --- |
| category | String | Product type   `SPOT` Spot trading   `MARGIN` Margin trading   `USDT-FUTURES`: USDT futures   `COIN-FUTURES`: Coin-M futures   `USDC-FUTURES`: USDC futures |
| symbol | String | Symbol name |
| isRwa | String | Is this an RWA Symbol  `YES`   `NO` |
| baseCoin | String | Base coin  e.g.,`BTC`in`BTCUSDT` |
| quoteCoin | String | Quote coin  e.g.,`USDT`in`BTCUSDT` |
| buyLimitPriceRatio | String | Buy price limit ratio   The ratio of the buy limit price to the market price, determining the maximum price at which a buy order will be placed |
| sellLimitPriceRatio | String | Sell price limit ratio   The ratio of the sell limit price to the market price, determining the minimum price at which a sell order will be placed |
| feeRateUpRatio | String | Fee markup ratio  The percentage by which the actual fee is increased relative to the base fee |
| openCostUpRatio | String | Opening cost markup ratio   The percentage by which the cost of opening a trading position is increased relative to the base or standard cost |
| minOrderQty | String | Minimum order quantity  This refers to the smallest allowable quantity for placing an order in terms of the base coin   Only applicable to futures trading, for spot/margin, please refer to [Trading Rules](https://www.bitget.com/zh-CN/trade-info/trade-rule). |
| maxOrderQty | String | Maximum order quantity for a single limit order  This refers to the largest allowable quantity for placing an order in terms of the base coin   Only applicable to futures trading, for spot/margin, please refer to [Trading Rules](https://www.bitget.com/zh-CN/trade-info/trade-rule). |
| minOrderAmount | String | Minimum order amount   This refers to the smallest allowable amount for placing an order in terms of the quote coin |
| pricePrecision | String | Price precision   The number of decimal places allowed for the price |
| quantityPrecision | String | Quantity precision   The number of decimal places allowed for the quantity |
| quotePrecision | String | Market order precision   The number of decimal places allowed for the price of the quote coin |
| priceMultiplier | String | Price multiplier   Used for futures orders, along with `pricePrecision`   Example: `pricePrecision`: 2 & `priceMultiplier`: 0.02 The order price must be a multiple of `priceMultiplier` and have two decimal places (e.g.,0.08, 1.14, 2.36) |
| quantityMultiplier | String | Quantity multiplier   Used for futures orders, along with `quantityPrecision`   Example: `quantityPrecision`: 2 & `quantityMultiplier`: 0.02 The order quantity must be a multiple of `quantityMultiplier` and have two decimal places (e.g.,0.08, 1.14, 2.36) |
| type | String | Futures type   `perpetual` Perpetual   `delivery` Delivery |
| maxSymbolOrderNum | String | Maximum order number in terms of the trading pair |
| maxProductOrderNum | String | Maximum order number in terms of the product line |
| maxPositionNum | String | Maximum position number in terms of the trading pair |
| status | String | Trading pair status   `listed` Listed (not yet open)   `online` Normal   `limit_open` Order placement restricted   `offline` Delisted/under maintenance   `restrictedAPI` API restricted |
| offTime | String | Delisting time   If not configured, it returns: "" |
| limitOpenTime | String | Restricted open time   If not configured, it returns: ""; Other values indicate symbol is under/expected maintenance and trading is prohibited after a specified time |
| deliveryTime | String | Delivery time   Available only for deliveries |
| deliveryStartTime | String | Delivery start time   Available only for deliveries |
| deliveryPeriod | String | Delivery period   `this_quarter` This quarter   `next_quarter` Next quarter   Available only for deliveries |
| fundInterval | String | Funding Interval   `1` Every 1 hour  `8` Every 8 hours |
| minLeverage | String | Minimum leverage |
| maxLeverage | String | Maximum leverage |
| maintainTime | String | Maintenance time   If not configured, it returns: "" |
| isIsolatedBaseBorrowable | String | Base coin borrowable status   Available only for margin trading |
| isIsolatedQuotedBorrowable | String | Quote coin borrowable status   Available only for margin trading |
| warningRiskRatio | String | Warning risk ratio |
| liquidationRiskRatio | String | Liquidation risk ratio |
| maxCrossedLeverage | String | Maximum leverage for cross margin   Available only for margin trading |
| maxIsolatedLeverage | String | Maximum leverage for isolated margin   Available only for margin trading |
| userMinBorrow | String | Minimum borrowable amount   Available only for margin trading |
| areaSymbol | String | Area symbol  `YES`/`NO`   Available only for Spot trading |
| maxMarketOrderQty | String | Maximum order quantity for a single market order  This refers to the largest allowable quantity for placing an order in terms of the base coin |