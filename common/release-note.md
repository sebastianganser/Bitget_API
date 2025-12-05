# V2 API Update Guide

## Scope of changes[​](#scope-of-changes "Direct link to Scope of changes")

### Interface aggregation[​](#interface-aggregation "Direct link to Interface aggregation")

In V1, interface changes involving modifications to input parameters are typically addressed by introducing new interfaces, ensuring minimal impact on online users. Therefore, in V2, we have optimized shortcomings such as interface redundancy and confusion in business scenarios. For detailed information on interface aggregation across all business lines, please refer to the V1 and V2 Interface Mapping Tables.

### Global symbol request rule changes[​](#global-symbol-request-rule-changes "Direct link to Global symbol request rule changes")

In V2, we reduced them to one parameter—**symbol**—corresponding to symbolName in V1. Additionally, business line notes such as SPBL and UMBCL were removed when passing the symbol value.

### Optimization of global query rules[​](#optimization-of-global-query-rules "Direct link to Optimization of global query rules")

In terms of data retrieval for query interfaces, we have abandoned the pagination method of pageSize and pageNo used in V1. In V2, we replaced it with cursor-based pagination with idLessThan and limit. Based on real-life business scenarios, a time range data query was added to most query interfaces. In addition, user ID can be used as the request parameter in precise query scenarios with some trade record, trade execution, and order-related interfaces. The basic rules and scenarios for id, startTime, endTime, idLessThan, and limit are described as follows:

  
Basic rule: When querying data, the verification order for returned results is id > startTime + endTime > idLessThan. In other words, it first prioritizes precise queries using the id, then narrows down the data range with startTime and endTime, and finally uses the cursor idLessThan to retrieve a specified number of data entries based on the limit.

### Standardization of naming rules for business line interfaces and parameters[​](#standardization-of-naming-rules-for-business-line-interfaces-and-parameters "Direct link to Standardization of naming rules for business line interfaces and parameters")

In V1, there was a lack of consistency in parameters between business lines. Therefore, in V2, we have standardized the naming and format of parameters with the same meaning for scenarios spanning different business lines (spot, futures, leverage) and interface types (Rest/WebSocket).

### Clearer catalog categorization[​](#clearer-catalog-categorization "Direct link to Clearer catalog categorization")

In V1, the categorization of interface catalogs was too vague, resulting in an excessive number of interfaces in some catalogs. This, in turn, led to difficulties in documentation query and poor user experience. In V2, we have adjusted the categorization and naming of the interface catalogs, making them more detailed, intuitive, thus avoiding readability and retrieval issues.

### Accessibility of more in-depth information[​](#accessibility-of-more-in-depth-information "Direct link to Accessibility of more in-depth information")

For futures and spot trading pairs, we significantly increased the trading pair depth that can be accessed through the interfaces and standardized the tiers across different business lines.

| Business Line | Version | Tier |
| --- | --- | --- |
| Spot | V1 | 150/200 |
| Spot | V2 | 1/5/15/50/max; default: 100. The max is determined by the highest tier available for the designated trading pair. |
| Future | V1 | 5/15/50/100 |
| Future | V2 | 1/5/15/50/max; default: 100.The max is determined by the highest tier available for the designated trading pair. |

### Merge of futures trigger order and trailing stop-loss[​](#merge-of-futures-trigger-order-and-trailing-stop-loss "Direct link to Merge of futures trigger order and trailing stop-loss")

In V2, we combined the trigger order and the trailing stop-loss into one, using the field planType to differentiate the order type.

The order placing conditions of the two are different. Different from the normal trigger order, the trailing stop-loss requires attention to the field callbackRatio, which is used to set the order-triggering percentage. stopSurplusTriggerPrice and stopLossTriggerPrice also require special attention as these two fields are used to determine the trail variance percentage that triggers the trailing stop-loss and take-profit orders.

### Position opening/closing in futures order placement[​](#position-openingclosing-in-futures-order-placement "Direct link to Position opening/closing in futures order placement")

In V2, we improved operations on positions in both one-way and hedging modes.

When placing an order, the field side and tradeSide are combined for parameter entry based on the position mode and direction.

Enumeration values of **side** and **tradeSide**:

| Field name | Enumeration value | Description |
| --- | --- | --- |
| side | buy | Buying |
| side | sell | selling |
| tradeSide | open | Opening a position |
| tradeSide | close | Closing a position |

Operation rules of parameter entries in one-way or hedging modes:

| Position mode | Parameter entries | Operation | Description |
| --- | --- | --- | --- |
| One-way mode | side: buy | Buying | In one-way mode, only one side is needed to indicate whether it is a buying or selling order |
| One-way mode | side: sell | Selling | In one-way mode, only one side is needed to indicate whether it is a buying or selling order |
| Hedging mode | side: buy; tradeSide: open | Opening a long position | In hedging mode, both side and tradeSide are needed to determine whether it is opening long/short or closing long/short |
| Hedging mode | side: sell; tradeSide: open | Opening a short position | In hedging mode, both side and tradeSide are needed to determine whether it is opening long/short or closing long/short |
| Hedging mode | side: buy; tradeSide: close | Closing a long position | In hedging mode, both side and tradeSide are needed to determine whether it is opening long/short or closing long/short |
| Hedging mode | side: sell; tradeSide: close | Closing a short position | In hedging mode, both side and tradeSide are needed to determine whether it is opening long/short or closing long/short |

### Optimization of delivery futures[​](#optimization-of-delivery-futures "Direct link to Optimization of delivery futures")

In V2, we updated the naming rules for symbol in Coin-M delivery futures.

For Coin-M delivery futures, the format of symbol is trading pair + month code + year.

Examples and descriptions:

| Symbol | Descriptions |
| --- | --- |
| BTCUSD**H**23 | H means March (Q1) and 23 means the year 2023 |
| BTCUSD**M**23 | M means June (Q2) and 23 means the year 2023 |
| BTCUSD**U**23 | U means September (Q3) and 23 means the year 2023 |
| BTCUSD**Z**23 | Z means December (Q4) and 23 means the year 2023 |

The bolded letters H, M, U, and Z are some of the month codes. Month codes:

| Month code | Month | Month code | Month |
| --- | --- | --- | --- |
| F | January | N | July |
| G | February | Q | August |
| `H` | March | `U` | September |
| J | April | V | October |
| K | May | X | November |
| `M` | June | `Z` | December |

### Optimized maximum/minimum order size logic of trading pairs[​](#optimized-maximumminimum-order-size-logic-of-trading-pairs "Direct link to Optimized maximum/minimum order size logic of trading pairs")

In V2, we have included parameter descriptions for maximum and minimum order sizes in interfaces that access spot and futures trading pairs. This enhancement enables users to access essential information about trading pairs, including minimum and maximum trading volumes, the maximum number of open orders (considering both trading pairs and products), price precision, amount precision, and other basic information.

### Earn interfaces coming soon[​](#earn-interfaces-coming-soon "Direct link to Earn interfaces coming soon")

To meet users' demand for crypto Earn products, we are about to launch interfaces for Savings and Shark Fin, covering features such as information retrieval, PnL statistics, asset analysis, subscription, and redemption. Both fixed and flexible Savings are supported, enhancing our digital asset management service.

### Crypto Loan interfaces coming soon[​](#crypto-loan-interfaces-coming-soon "Direct link to Crypto Loan interfaces coming soon")

Catering to the needs of investors seeking more conservative or flexible approaches to grow their wealth, we are about to launch interfaces for Crypto Loan. For users with lower risk tolerance who seek conservative and flexible borrowing solutions, we introduced the interface for Crypto Loan. Crypto Loan is a financial product that allows users to borrow fiat currency or cryptocurrencies by using their crypto assets as collateral.

  
  
The Bitget Crypto Loan API aims to help users get additional funds instantly without losing control over their own crypto assets.The whole process includes staking the collateral, obtaining the loan, adding to/withdrawing from the collateral, undergoing liquidation, paying interest, repaying the loan, and redeeming the collateral. It should be noted that, due to the nature of the digital currency market, the crypto market is considerably more volatile than the traditional market. As a result, future fluctuations in coin prices will impact the overall return.

## Interface Mapping Tables[​](#interface-mapping-tables "Direct link to Interface Mapping Tables")

### Spot[​](#spot "Direct link to Spot")

| V1 Endpoint | V2 Endpoint |
| --- | --- |
| - GET /api/spot/v1/notice/queryAllNotices | - GET /api/v2/public/annoucements |
| - GET /api/spot/v1/public/time | - GET /api/v2/public/time |
| - GET /api/spot/v1/public/currencies | - GET /api/v2/spot/public/coins |
| - GET /api/spot/v1/public/products | - GET /api/v2/spot/public/symbols |
| - GET /api/spot/v1/public/product | - GET /api/v2/spot/public/symbols |
| - GET /api/spot/v1/market/ticker | - GET /api/v2/spot/market/tickers |
| - GET /api/spot/v1/market/tickers | - GET /api/v2/spot/market/tickers |
| - GET /api/spot/v1/market/fills-history | - GET /api/v2/spot/market/fills-history |
| - GET /api/spot/v1/market/fills | - GET /api/v2/spot/market/fills |
| - GET /api/spot/v1/market/candles | - GET /api/v2/spot/market/candles |
| - GET /api/spot/v1/market/history-candles | - GET /api/v2/spot/market/history-candles |
| - GET /api/spot/v1/market/depth | - GET /api/v2/spot/market/orderbook |
| - GET /api/spot/v1/market/merge-depth | - GET /api/v2/spot/market/orderbook |
| - GET /api/spot/v1/market/spot-vip-level | - GET /api/v2/spot/market/vip-fee-rate |
| - POST /api/spot/v1/wallet/transfer | - POST /api/v2/spot/wallet/transfer |
| - POST /api/spot/v1/wallet/transfer-v2 | - POST /api/v2/spot/wallet/transfer |
| - POST /api/spot/v1/wallet/subTransfer | - POST /api/v2/spot/wallet/subaccount-transfer |
| - POST /api/spot/v1/wallet/withdrawal | - POST /api/v2/spot/wallet/withdrawal |
| - POST /api/spot/v1/wallet/withdrawal-v2 | - POST /api/v2/spot/wallet/withdrawal |
| - POST /api/spot/v1/wallet/withdrawal-inner | - POST /api/v2/spot/wallet/withdrawal |
| - POST /api/spot/v1/wallet/withdrawal-inner-v2 | - POST /api/v2/spot/wallet/withdrawal |
| - GET /api/spot/v1/wallet/deposit-address | - GET /api/v2/spot/wallet/deposit-address |
| - GET /api/spot/v1/wallet/deposit-list | - GET /api/v2/spot/wallet/deposit-records |
| - GET /api/spot/v1/wallet/withdrawal-list | - GET /api/v2/spot/wallet/withdrawal-records |
| - GET /api/user/v1/fee/query | - GET /api/v2/public/trade-rate |
| - GET /api/spot/v1/account/getInfo | - GET /api/v2/spot/account/info |
| - GET /api/spot/v1/account/assets | - GET /api/v2/spot/account/assets |
| - GET /api/spot/v1/account/assets-lite | - GET /api/v2/spot/account/assets |
| - POST /api/spot/v1/account/sub-account-spot-assets | - GET /api/v2/spot/account/subaccount-assets |
| - POST /api/spot/v1/account/bills | - GET /api/v2/spot/account/bills |
| - GET /api/spot/v1/account/transferRecords | - GET /api/v2/spot/account/transferRecords |
| - POST /api/spot/v1/trade/orders | - POST /api/v2/spot/trade/place-order |
| - POST /api/spot/v1/trade/batch-orders | - POST /api/v2/spot/trade/batch-orders |
| - POST /api/spot/v1/trade/cancel-order | - POST /api/v2/spot/trade/cancel-order |
| - POST /api/spot/v1/trade/cancel-order-v2 | - POST /api/v2/spot/trade/cancel-order |
| - POST /api/spot/v1/trade/cancel-symbol-order | - POST /api/v2/spot/trade/cancel-symbol-order |
| - POST /api/spot/v1/trade/cancel-batch-orders | - POST /api/v2/spot/trade/batch-cancel-order |
| - POST /api/spot/v1/trade/cancel-batch-orders-v2 | - POST /api/v2/spot/trade/batch-cancel-order |
| - POST /api/spot/v1/trade/orderInfo | - GET /api/v2/spot/trade/orderInfo |
| - POST /api/spot/v1/trade/open-order | - GET /api/v2/spot/trade/unfilled-orders |
| - POST /api/spot/v1/trade/history | - GET /api/v2/spot/trade/history-orders |
| - POST /api/spot/v1/trade/fills | - GET /api/v2/spot/trade/fills |
| - POST /api/spot/v1/plan/placePlan | - POST /api/v2/spot/trade/place-plan-order |
| - POST /api/spot/v1/plan/modifyPlan | - POST /api/v2/spot/trade/modify-plan-order |
| - POST /api/spot/v1/plan/cancelPlan | - POST /api/v2/spot/trade/cancel-plan-order |
| - POST /api/spot/v1/plan/currentPlan | - GET /api/v2/spot/trade/current-plan-order |
| - POST /api/spot/v1/plan/historyPlan | - GET /api/v2/spot/trade/history-plan-order |
| - POST /api/spot/v1/plan/batchCancelPlan | - POST /api/v2/spot/trade/batch-cancel-plan-order |
| - GET /api/p2p/v1/merchant/merchantList | - GET /api/v2/p2p/merchantList |
| - GET /api/p2p/v1/merchant/merchantInfo | - GET /api/v2/p2p/merchantInfo |
| - GET /api/p2p/v1/merchant/advList | - GET /api/v2/p2p/advList |
| - GET /api/p2p/v1/merchant/orderList | - GET /api/v2/p2p/orderList |
| - POST /api/user/v1/sub/virtual-create | - POST /api/v2/user/create-virtual-subaccount |
| - POST /api/user/v1/sub/virtual-modify | - POST /api/v2/user/modify-virtual-subaccount |
| - POST /api/user/v1/sub/virtual-api-batch-create | - POST /api/v2/user/batch-create-subaccount-and-apikey |
| - GET /api/user/v1/sub/virtual-list | - GET /api/v2/user/virtual-subaccount-list |
| - POST /api/user/v1/sub/virtual-api-create | - POST /api/v2/user/create-virtual-subaccount-apikey |
| - POST /api/user/v1/sub/virtual-api-modify | - POST /api/v2/user/modify-virtual-subaccount-apikey |
| - GET /api/user/v1/sub/virtual-api-list | - GET /api/v2/user/virtual-subaccount-apikey-list |
| - GET /api/spot/v1/convert/currencies | - GET /api/v2/convert/currencies |
| - POST /api/spot/v1/convert/quoted-price | - POST /api/v2/convert/quoted-price |
| - POST /api/spot/v1/convert/trade | - POST /api/v2/convert/trade |
| - GET /api/spot/v1/convert/convert-record | - GET /api/v2/convert/convert-record |
| - GET /api/user/v1/tax/spot-record | - GET /api/v2/tax/spot-record |
| - GET /api/user/v1/tax/future-record | - GET /api/v2/tax/future-record |
| - GET /api/user/v1/tax/margin-record | - GET /api/v2/tax/margin-record |
| - GET /api/user/v1/tax/p2p-record | - GET /api/v2/tax/p2p-record |

### Future[​](#future "Direct link to Future")

| V1 Endpoint | V2 Endpoint |
| --- | --- |
| - GET /api/mix/v1/market/ticker | - GET /api/v2/mix/market/ticker |
| - GET /api/mix/v1/market/tickers | - GET /api/v2/mix/market/tickers |
| - GET /api/mix/v1/market/contract-vip-level | - GET /api/v2/mix/market/vip-fee-rate |
| - GET /api/mix/v1/market/fills | - GET /api/v2/mix/market/fills |
| - GET /api/mix/v1/market/fills-history | - GET /api/v2/mix/market/fills-history |
| - GET /api/mix/v1/market/candles | - GET /api/v2/mix/market/candles |
| - GET /api/mix/v1/market/history-candles | - GET /api/v2/mix/market/history-candles |
| - GET /api/mix/v1/market/history-index-candles | - GET /api/v2/mix/market/history-index-candles |
| - GET /api/mix/v1/market/history-mark-candles | - GET /api/v2/mix/market/history-mark-candles |
| - GET /api/mix/v1/market/funding-time | - GET /api/v2/mix/market/funding-time |
| - GET /api/mix/v1/market/history-fundRate | - GET /api/v2/mix/market/history-fund-rate |
| - GET /api/mix/v1/market/current-fundRate | - GET /api/v2/mix/market/current-fund-rate |
| - GET /api/mix/v1/market/open-interest | - GET /api/v2/mix/market/open-interest |
| - GET /api/mix/v1/market/queryPositionLever | - GET /api/v2/mix/market/query-position-lever |
| - GET /api/mix/v1/account/account | - GET /api/v2/mix/account/account |
| - GET /api/mix/v1/account/accounts | - GET /api/v2/mix/account/accounts |
| - POST /api/mix/v1/account/sub-account-contract-assets | - GET /api/v2/mix/account/sub-account-assets |
| - POST /api/mix/v1/account/open-count | - GET /api/v2/mix/account/open-count |
| - POST /api/mix/v1/account/setLeverage | - POST /api/v2/mix/account/set-leverage |
| - POST /api/mix/v1/account/setMargin | - POST /api/v2/mix/account/set-margin |
| - POST /api/mix/v1/account/setMarginMode | - POST /api/v2/mix/account/set-margin-mode |
| - POST /api/mix/v1/account/setPositionMode | - POST /api/v2/mix/account/set-position-mode |
| - GET /api/mix/v1/position/singlePosition | - GET /api/v2/mix/position/single-position |
| - GET /api/mix/v1/position/singlePosition-v2 | - GET /api/v2/mix/position/single-position |
| - GET /api/mix/v1/position/allPosition | - GET /api/v2/mix/position/all-position |
| - GET /api/mix/v1/position/allPosition-v2 | - GET /api/v2/mix/position/all-position |
| - GET /api/mix/v1/account/accountBill | - GET /api/v2/mix/account/bill |
| - GET /api/mix/v1/account/accountBusinessBill | - GET /api/v2/mix/account/bill |
| - GET /api/mix/v1/market/index | - GET /api/v2/mix/market/symbol-price |
| - GET /api/mix/v1/market/mark-price | - GET /api/v2/mix/market/symbol-price |
| - GET /api/mix/v1/market/contracts | - GET /api/v2/mix/market/contracts |
| - GET /api/mix/v1/market/symbol-leverage | - GET /api/v2/mix/market/contracts |
| - GET /api/mix/v1/market/open-limit | - GET /api/v2/mix/market/contracts |
| - POST /api/mix/v1/plan/placePlan | - POST /api/v2/mix/order/place-plan-order |
| - POST /api/mix/v1/plan/placeTrailStop | - POST /api/v2/mix/order/place-plan-order |
| - POST /api/mix/v1/plan/modifyPlan | - POST /api/v2/mix/order/modify-plan-order |
| - POST /api/mix/v1/plan/modifyPlanPreset | - POST /api/v2/mix/order/modify-plan-order |
| - POST /api/mix/v1/plan/cancelPlan | - POST /api/v2/mix/order/cancel-plan-order |
| - POST /api/mix/v1/plan/cancelSymbolPlan | - POST /api/v2/mix/order/cancel-plan-order |
| - POST /api/mix/v1/order/cancel-batch-orders | - POST /api/v2/mix/order/batch-cancel-orders |
| - POST /api/mix/v1/order/cancel-all-orders | - POST /api/v2/mix/order/batch-cancel-orders |
| - POST /api/mix/v1/order/cancel-symbol-orders | - POST /api/v2/mix/order/batch-cancel-orders |
| - GET /api/mix/v1/order/current | - GET /api/v2/mix/order/orders-pending |
| - GET /api/mix/v1/order/marginCoinCurrent | - GET /api/v2/mix/order/orders-pending |
| - GET /api/mix/v1/order/history | - GET api/v2/mix/order/orders-history |
| - GET /api/mix/v1/order/historyProductType | - GET api/v2/mix/order/orders-history |
| - GET /api/mix/v1/order/fills | - GET /api/v2/mix/order/fills |
| - GET /api/mix/v1/order/allFills | - GET /api/v2/mix/order/fills |
| - POST /api/mix/v1/order/placeOrder | - POST /api/v2/mix/order/place-order |
| - POST /api/mix/v1/order/placeOrder | - POST /api/v2/mix/order/click-backhand |
| - POST /api/mix/v1/order/batch-orders | - POST /api/v2/mix/order/batch-place-order |
| - POST /api/mix/v1/order/cancel-order | - POST /api/v2/mix/order/cancel-order |
| - POST /api/mix/v1/order/modifyOrder | - POST /api/v2/mix/order/modify-order |
| - POST /api/mix/v1/order/close-all-positions | - POST /api/v2/mix/order/close-positions |
| - GET /api/mix/v1/order/detail | - GET /api/v2/mix/order/detail |
| N/A | - GET /api/v2/mix/order/orders-plan-pending |
| N/A | - GET /api/v2/mix/order/orders-plan-history |

### Margin[​](#margin "Direct link to Margin")

| V1 Endpoint | V2 Endpoint |
| --- | --- |
| - GET /api/margin/v1/cross/public/interestRateAndLimit | - GET /api/v2/margin/cross/interest-rate-and-limit |
| - GET /api/margin/v1/isolated/public/interestRateAndLimit | - GET /api/v2/margin/isolated/interest-rate-and-limit |
| - GET /api/margin/v1/cross/public/tierData | - GET /api/v2/margin/cross/tier-data |
| - GET /api/margin/v1/isolated/public/tierData | - GET /api/v2/margin/isolated/tier-data |
| - GET /api/margin/v1/public/currencies | - GET /api/v2/margin/currencies |
| - GET /api/margin/v1/cross/account/assets | - GET /api/v2/margin/cross/account/assets |
| - GET /api/margin/v1/isolated/account/assets | - GET /api/v2/margin/isolated/account/assets |
| - POST /api/margin/v1/cross/account/borrow | - POST /api/v2/margin/cross/account/borrow |
| - POST /api/margin/v1/isolated/account/borrow | - POST /api/v2/margin/isolated/account/borrow |
| - POST /api/margin/v1/cross/account/repay | - POST /api/v2/margin/cross/account/repay |
| - GET /api/margin/v1/isolated/account/repay | - POST /api/v2/margin/cross/account/repay |
| - GET /api/margin/v1/cross/account/riskRate | - GET /api/v2/margin/cross/account/risk-rate |
| - POST /api/margin/v1/isolated/account/riskRate | - GET /api/v2/margin/cross/account/risk-rate |
| - POST /api/margin/v1/cross/account/maxBorrowableAmount | - GET /api/v2/margin/cross/account/max-borrowable-amount |
| - GET /api/margin/v1/isolated/account/maxBorrowableAmount | - GET /api/v2/margin/isolated/account/max-borrowable-amount |
| - GET /api/margin/v1/cross/account/maxTransferOutAmount | - GET /api/v2/margin/cross/account/max-transfer-out-amount |
| - GET /api/margin/v1/isolated/account/maxTransferOutAmount | - GET /api/v2/margin/isolated/account/max-transfer-out-amount |
| - POST /api/margin/v1/isolated/account/flashRepay | - POST /api/v2/margin/isolated/account/flash-repay |
| - POST /api/margin/v1/isolated/account/queryFlashRepayStatus | - POST /api/v2/margin/isolated/account/query-flash-repay-status |
| - POST /api/margin/v1/cross/account/flashRepay | - POST /api/v2/margin/cross/account/flash-repay |
| - POST /api/margin/v1/cross/account/queryFlashRepayStatus | - POST /api/v2/margin/cross/account/flash-repay-status |
| - POST /api/margin/v1/isolated/order/placeOrder | - POST /api/v2/margin/isolated/place-order |
| - POST /api/margin/v1/isolated/order/batchPlaceOrder | - POST /api/v2/margin/isolated/batch-place-order |
| - POST /api/margin/v1/isolated/order/cancelOrder | - POST /api/v2/margin/isolated/cancel-order |
| - POST /api/margin/v1/isolated/order/batchCancelOrder | - POST /api/v2/margin/isolated/batch-cancel-order |
| - GET /api/margin/v1/isolated/order/openOrders | - GET /api/v2/margin/isolated/open-orders |
| - GET /api/margin/v1/isolated/order/history | - GET /api/v2/margin/isolated/history-orders |
| - GET /api/margin/v1/isolated/order/fills | - GET /api/v2/margin/isolated/fills |
| - GET /api/margin/v1/isolated/loan/list | - GET /api/v2/margin/isolated/borrow-history |
| - GET /api/margin/v1/isolated/repay/list | - GET /api/v2/margin/isolated/repay-history |
| - GET /api/margin/v1/isolated/interest/list | - GET /api/v2/margin/isolated/interest-history |
| - GET /api/margin/v1/isolated/liquidation/list | - GET /api/v2/margin/isolated/liquidation-history |
| - GET /api/margin/v1/isolated/fin/list | - GET /api/v2/margin/isolated/financial-records |
| - POST /api/margin/v1/cross/order/placeOrder | - POST /api/v2/margin/cross/place-order |
| - POST /api/margin/v1/cross/order/batchPlaceOrder | - POST /api/v2/margin/cross/batch-place-order |
| - POST /api/margin/v1/cross/order/cancelOrder | - POST /api/v2/margin/cross/cancel-order |
| - POST /api/margin/v1/cross/order/batchCancelOrder | - POST /api/v2/margin/cross/batch-cancel-order |
| - GET /api/margin/v1/cross/order/openOrders | - GET /api/v2/margin/cross/open-orders |
| - GET /api/margin/v1/cross/order/history | - GET /api/v2/margin/cross/history-orders |
| - GET /api/margin/v1/cross/order/fills | - GET /api/v2/margin/cross/fills |
| - GET /api/margin/v1/cross/loan/list | - GET /api/v2/margin/cross/borrow-history |
| - GET /api/margin/v1/cross/repay/list | - GET /api/v2/margin/cross/repay-history |
| - GET /api/margin/v1/cross/interest/list | - GET /api/v2/margin/cross/interest-history |
| - GET /api/margin/v1/cross/liquidation/list | - GET /api/v2/margin/cross/liquidation-history |
| - GET /api/margin/v1/cross/fin/list | - GET /api/v2/margin/cross/financial-records |

### Broker[​](#broker "Direct link to Broker")

| V1 Endpoint | V2 Endpoint |
| --- | --- |
| - GET /api/broker/v1/account/info | - GET /api/v2/broker/account/info |
| - POST /api/broker/v1/account/sub-create | - POST /api/v2/broker/account/create-subaccount |
| - GET /api/broker/v1/account/sub-list | - GET /api/v2/broker/account/subaccount-list |
| - POST /api/broker/v1/account/sub-modify | - POST /api/v2/broker/account/modify-subaccount |
| - POST /api/broker/v1/account/sub-modify-email | - POST /api/v2/broker/account/modify-subaccount-email |
| - GET /api/broker/v1/account/sub-email | - GET /api/v2/broker/account/subaccount-email |
| - GET /api/broker/v1/account/sub-spot-assets | - GET /api/v2/broker/account/subaccount-spot-assets |
| - GET /api/broker/v1/account/sub-future-assets | - GET /api/v2/broker/account/subaccount-future-assets |
| - POST /api/broker/v1/account/sub-address | - POST /api/v2/broker/account/subaccount-address |
| - POST /api/broker/v1/account/sub-withdrawal | - POST /api/v2/broker/account/subaccount-withdrawal |
| - POST /api/broker/v1/account/sub-auto-transfer | - POST /api/v2/broker/account/set-subaccount-autotransfer |
| - POST /api/broker/v1/manage/sub-api-create | - POST /api/v2/broker/manage/create-subaccount-apikey |
| - GET /api/broker/v1/manage/sub-api-list | - GET /api/v2/broker/manage/subaccount-apikey-list |
| - POST /api/broker/v1/manage/sub-api-modify | - POST /api/v2/broker/manage/modify-subaccount-apikey |

### Future Copy Trading[​](#future-copy-trading "Direct link to Future Copy Trading")

| V1 Endpoint | V2 Endpoint |
| --- | --- |
| - POST /api/mix/v1/trace/closeTrackOrder | - POST /api/v2/copy/mix-trader/order-close-positions |
| - POST /api/mix/v1/trace/closeTrackOrderBySymbol | - POST /api/v2/copy/mix-trader/order-close-positions |
| - GET /api/mix/v1/trace/currentTrack | - GET /api/v2/copy/mix-trader/order-current-track |
| - GET /api/mix/v1/trace/historyTrack | - GET /api/v2/copy/mix-trader/order-history-track |
| - POST /api/mix/v1/trace/modifyTPSL | - POST /api/v2/copy/mix-trader/order-modify-tpsl |
| - GET /api/mix/v1/trace/traderDetail | - GET /api/v2/copy/mix-trader/order-total-detail |
| - GET /api/mix/v1/trace/summary | - GET /api/v2/copy/mix-trader/profit-summarys |
| - GET /api/mix/v1/trace/profitSettleTokenIdGroup | - GET /api/v2/copy/mix-trader/profit-summarys |
| - GET /api/mix/v1/trace/profitDateList | - GET /api/v2/copy/mix-trader/profit-hisotry-details |
| - GET /api/mix/v1/trace/waitProfitDateList | - GET /api/v2/copy/mix-trader/profit-details |
| - GET /api/mix/v1/trace/profitDateGroupList | - GET /api/v2/copy/mix-trader/profits-group-coin-date |
| - GET /api/mix/v1/trace/traderSymbols | - GET /api/v2/copy/mix-trader/config-query-symbols |
| - POST /api/mix/v1/trace/queryTraderTpslRatioConfig | - GET /api/v2/copy/mix-trader/config-query-symbols |
| - POST /api/mix/v1/trace/setUpCopySymbols | - POST /api/v2/copy/mix-trader/config-setting-symbols |
| - POST /api/mix/v1/trace/traderUpdateTpslRatioConfig | - POST /api/v2/copy/mix-trader/config-setting-symbols |
| - POST /api/mix/v1/trace/traderUpdateConfig | - POST /api/v2/copy/mix-trader/config-settings-base |
| - GET /api/mix/v1/trace/myFollowerList | - GET /api/v2/copy/mix-trader/config-query-followers |
| - POST /api/mix/v1/trace/removeFollower | - POST /api/v2/copy/mix-trader/config-remove-follower |
| - POST /api/mix/v1/trace/followerCloseByTrackingNo | - POST /api/v2/copy/mix-follower/close-positions |
| - POST /api/mix/v1/trace/followerCloseByAll | - POST /api/v2/copy/mix-follower/close-positions |
| - GET /api/mix/v1/trace/followerOrder | - GET /api/v2/copy/mix-follower/query-current-orders |
| - GET /api/mix/v1/trace/followerHistoryOrders | - GET /api/v2/copy/mix-follower/query-history-orders |
| - POST /api/mix/v1/trace/followerSetTpsl | - POST /api/v2/copy/mix-follower/setting-tpsl |
| - GET /api/mix/v1/trace/queryTraceConfig | - GET /api/v2/copy/mix-follower/query-settings |
| - GET /api/mix/v1/trace/public/getFollowerConfig | - GET /api/v2/copy/mix-follower/query-quantity-limit |
| - POST /api/mix/v1/trace/followerSetBatchTraceConfig | - POST /api/v2/copy/mix-follower/settings |
| - POST /api/mix/v1/trace/cancelCopyTrader | - POST /api/v2/copy/mix-follower/cancel-trader |
| - GET /api/mix/v1/trace/myTraderList | - GET /api/v2/copy/mix-follower/query-traders |
| - GET /api/mix/v1/trace/traderList | - GET /api/v2/copy/mix-broker/query-traders |
| - GET /api/mix/v1/trace/report/order/historyList | - GET /api/v2/copy/mix-broker/query-history-traces |
| - GET /api/mix/v1/trace/report/order/currentList | - GET /api/v2/copy/mix-broker/query-current-traces |

### Spot Copy Trading[​](#spot-copy-trading "Direct link to Spot Copy Trading")

| V1 Endpoint | V2 Endpoint |
| --- | --- |
| - POST /api/spot/v1/trace/profit/totalProfitInfo | - GET /api/v2/copy/spot-trader/profit-summarys |
| - POST /api/spot/v1/trace/profit/totalProfitList | - GET /api/v2/copy/spot-trader/profit-summarys |
| - POST /api/spot/v1/trace/profit/profitHisList | - GET /api/v2/copy/spot-trader/profit-summarys |
| - POST /api/spot/v1/trace/profit/profitHisDetailList | - GET /api/v2/copy/spot-trader/profit-hisotry-details |
| - POST /api/spot/v1/trace/profit/waitProfitDetailList | - GET /api/v2/copy/spot-trader/profit-details |
| - POST /api/spot/v1/trace/order/orderCurrentList | - GET /api/v2/copy/spot-trader/order-current-track |
| - POST /api/spot/v1/trace/order/orderHistoryList | - GET /api/v2/copy/spot-trader/order-history-track |
| - POST /api/spot/v1/trace/order/updateTpsl | - POST /api/v2/copy/spot-trader/order-modify-tpsl |
| - POST /api/spot/v1/trace/order/closeTrackingOrder | - POST /api/v2/copy/spot-trader/order-close-tracking |
| - POST /api/spot/v1/trace/user/getTraderInfo | - GET /api/v2/copy/spot-trader/order-total-detail |
| - POST /api/spot/v1/trace/config/getTraderSettings | - GET /api/v2/copy/spot-trader/config-query-settings |
| - POST /api/spot/v1/trace/order/spotInfoList | - GET /api/v2/copy/spot-trader/config-query-settings |
| - POST /api/spot/v1/trace/config/getRemoveFollowerConfig | - GET /api/v2/copy/spot-trader/config-query-settings |
| - POST /api/spot/v1/trace/user/myFollowers | - GET /api/v2/copy/spot-trader/config-query-followers |
| - POST /api/spot/v1/trace/config/setProductCode | - POST /api/v2/copy/spot-trader/config-setting-symbols |
| - POST /api/spot/v1/trace/user/removeFollower | - POST /api/v2/copy/spot-trader/config-remove-follower |
| N/A | - GET /api/v2/copy/spot-follower/query-current-orders |
| N/A | - GET /api/v2/copy/mix-follower/query-history-orders |
| N/A | - POST /api/v2/copy/spot-follower/setting-tpsl |
| N/A | - POST /api/v2/copy/spot-follower/order-close-tracking |
| - POST /api/spot/v1/trace/config/getFollowerSettings | - GET /api/v2/copy/spot-follower/query-settings |
| - POST /api/spot/v1/trace/user/myTraders | - GET /api/v2/copy/spot-follower/query-traders |
| - POST /api/spot/v1/trace/config/setFollowerConfig | - POST /api/v2/copy/spot-follower/settings |
| - POST /api/spot/v1/trace/user/removeTrader | - POST /api/v2/copy/spot-follower/cancel-trader |
| - POST /api/spot/v1/trace/order/followerEndOrder | - POST /api/v2/copy/spot-follower/stop-order |
| N/A | - GET /api/v2/copy/spot-follower/query-trader-symbols |