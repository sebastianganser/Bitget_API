# Change Log

## [November 28, 2025]The maximum number of returned entries for the candlestick API has been increased to 1,000.[​](#november-28-2025the-maximum-number-of-returned-entries-for-the-candlestick-api-has-been-increased-to-1000 "Direct link to november-28-2025the-maximum-number-of-returned-entries-for-the-candlestick-api-has-been-increased-to-1000")

Interface:

* /api/v3/market/candles

Changes：

* The maximum number of returned entries for the candlestick API has been increased to 1,000.

## [November 28, 2025] New API for Get Open Interest Limit.[​](#november-28-2025-new-api-for-get-open-interest-limit "Direct link to november-28-2025-new-api-for-get-open-interest-limit")

Interface：/api/v3/user/create-sub   
Changes：

* New API for Get Open Interest Limit.

## [November 26, 2025] Add instructions for switching to Advanced Mode when creating a new sub-account.[​](#november-26-2025-add-instructions-for-switching-to-advanced-mode-when-creating-a-new-sub-account "Direct link to november-26-2025-add-instructions-for-switching-to-advanced-mode-when-creating-a-new-sub-account")

Interface：/api/v3/user/create-sub   
Changes：

* Add instructions for switching to Advanced Mode when creating a new sub-account: Sub-accounts are created in Unified Account - Basic Mode by default. To switch to Advanced Mode, please set it manually on the web page.

# [November 26, 2025] Websocket Added a new platform liquidation push channel

Websocket: Liquidation channel   
Changes: Websocket Added a new platform liquidation push channel

## [November 26, 2025] Websocket Added new ADL notification channel[​](#november-26-2025-websocket-added-new-adl-notification-channel "Direct link to november-26-2025-websocket-added-new-adl-notification-channel")

Websocket: ADL notification channel   
Changes: Websocket Added new ADL notification channel

## [November 21, 2025] The return value of the get instruments API has added a new enumeration for status.[​](#november-21-2025-the-return-value-of-the-get-instruments-api-has-added-a-new-enumeration-for--status "Direct link to november-21-2025-the-return-value-of-the-get-instruments-api-has-added-a-new-enumeration-for--status")

Interface：/api/v3/market/instruments   
Changes：

* The return value of the get instruments API: a new enumeration value `limit_close` has been added to the `status` .

## [November 21, 2025] Add new tax API[​](#november-21-2025-add-new-tax-api "Direct link to november-21-2025-add-new-tax-api")

Interface：/api/v3/tax/records  
Changes：

* Add new tax API

## [November 12, 2025] WebSocket Order Modification Channel Adds Request Parameters[​](#november-12-2025-websocket-order-modification-channel-adds-request-parameters "Direct link to november-12-2025-websocket-order-modification-channel-adds-request-parameters")

Websocket: order modification channel   
Changes: The order modification channel now includes new request parameters: category and symbol.

## [November 8, 2025] WebSocket Supports Broker API Code[​](#november-8-2025-websocket-supports-broker-api-code "Direct link to november-8-2025-websocket-supports-broker-api-code")

Websocket: place order channel   
Changes: The order placement channel supports passing the Broker API Code to receive rebates.

## [October 29, 2025] Added API for retrieving the maximum transferable amount.[​](#october-29-2025-added-api-for-retrieving-the-maximum-transferable-amount "Direct link to october-29-2025-added-api-for-retrieving-the-maximum-transferable-amount")

Interface：/api/v3/account/max-transferable  
Changes：

* Added API for retrieving the maximum transferable amount.

## [October 9, 2025] Notice: Optimization of Idempotency Rule for clientOid in Unified Account[​](#october-9-2025-notice-optimization-of-idempotency-rule-for-clientoid-in-unified-account "Direct link to october-9-2025-notice-optimization-of-idempotency-rule-for-clientoid-in-unified-account")

Affected APIs:   
REST API: Place Order, Batch Place Order   
REST API: Order Details   
WebSocket : Place Order, Batch Place Order   
Before Optimization: Based on a time limit, the validity period of clientOid does not exceed 2 hours.   
After Optimization: The time limit is removed, and the rule is optimized to be determined by the current order status. Specifically, clientOid cannot be duplicated during the order pending period; once the order is filled or canceled, clientOid can be duplicated.

## [September 26, 2025] New API for a sub-account initiates a transfer to the master account[​](#september-26-2025-new-api-for-a-sub-account-initiates-a-transfer-to-the-master-account "Direct link to september-26-2025-new-api-for-a-sub-account-initiates-a-transfer-to-the-master-account")

Interface：/api/v3/account/sub-master-transfer  
Changes：

* New API for a sub-account initiates a transfer to the master account

## [September 25, 2025] Candlestick and Historical Candlestick APIs Add Premium Index; Get Trading Product Information API Adds RWA Identifier Field[​](#september-25-2025-candlestick-and-historical-candlestick-apis-add-premium-index-get-trading-product-information-api-adds-rwa-identifier-field "Direct link to september-25-2025-candlestick-and-historical-candlestick-apis-add-premium-index-get-trading-product-information-api-adds-rwa-identifier-field")

Interface: /api/v3/market/candles、/api/v3/market/history-candles、/api/v3/market/instruments  
Changes：

* The K-Line Data and Historical K-Line Data APIs now include the Premium Index.
* The Get Trading Product Information API now includes the RWA identifier field.

## [September 23, 2025] Launch of WebSocket Order Modification and Batch Order Modification Channels[​](#september-23-2025-launch-of-websocket-order-modification-and-batch-order-modification-channels "Direct link to september-23-2025-launch-of-websocket-order-modification-and-batch-order-modification-channels")

WebSocket: Order Modification, Batch Order Modification Channels   
Changes： Newly added WebSocket Order Modification Channel and WebSocket Batch Order Modification Channel

## [September 2, 2025] Add reason field for Get Switch Status[​](#september-2-2025-add-reason-field-for-get-switch-status "Direct link to september-2-2025-add-reason-field-for-get-switch-status")

Interface: /api/v3/account/switch-status  
Changes：

* Add reason field for Get Switch Status

## [August 28, 2025] Notice: Optimization of Push Frequency for Websocket Order Book Channel (books1) in Unified Account (v3)[​](#august-28-2025-notice-optimization-of-push-frequency-for-websocket-order-book-channel-books1-in-unified-account-v3 "Direct link to august-28-2025-notice-optimization-of-push-frequency-for-websocket-order-book-channel-books1-in-unified-account-v3")

Websocket: Order Book Channel   
Adjustment Content: The push frequency of the order book channel (books1) is optimized to 20ms. The symbols for this optimization are: BTCUSDT, ETHUSDT, XRPUSDT, SOLUSDT, SUIUSDT, DOGEUSDT, ADAUSDT, PEPEUSDT, LINKUSDT, HBARUSDT

## [August 26, 2025] Announcement: New Scheduled Push Mechanism for WebSocket Account and Position Channels[​](#august-26-2025-announcement-new-scheduled-push-mechanism-for-websocket-account-and-position-channels "Direct link to august-26-2025-announcement-new-scheduled-push-mechanism-for-websocket-account-and-position-channels")

Websocket: `account` channel、`position` channel   
   
Adjustment: A new scheduled push mechanism has been added to the WebSocket Account and Position channels, with pushes at a fixed 5-second interval.

## [August 12, 2025] WebSocket futures market data channel adds nextFundingTime field.[​](#august-12-2025-websocket-futures-market-data-channel-adds-nextfundingtime-field "Direct link to august-12-2025-websocket-futures-market-data-channel-adds-nextfundingtime-field")

Websocket: futures ticker channel   
Adjustment: A new field nextFundingTime has been added to the WebSocket futures market data channel.

## [August 12, 2025] WebSocket order channel response adds "amount".[​](#august-12-2025-websocket-order-channel-response-adds-amount "Direct link to august-12-2025-websocket-order-channel-response-adds-amount")

Websocket: order channel   
Adjustment: The response parameters of the WebSocket order channel have added "amount"

## [August 12, 2025] The unified account execution API has added the Execution Correlation ID.[​](#august-12-2025-the-unified-account-execution-api-has-added-the-execution-correlation-id "Direct link to august-12-2025-the-unified-account-execution-api-has-added-the-execution-correlation-id")

Websocket: `publicTrade` channel、`fill` channel   
Interface: /api/v3/trade/fills、/api/v3/market/fills   
Adjustment: The unified account execution API has added the Execution Correlation ID.

## [August 8, 2025] Transaction details API adds category input and clientOid response.[​](#august-8-2025-transaction-details-api-adds-category-input-and-clientoid-response "Direct link to august-8-2025-transaction-details-api-adds-category-input-and-clientoid-response")

Interface：/api/v3/trade/fills   
Adjustment：

* Transaction details API adds category input and clientOid response.

## [August 8, 2025] Account settings API adds UID and account mode response.[​](#august-8-2025-account-settings-api-adds-uid-and-account-mode-response "Direct link to august-8-2025-account-settings-api-adds-uid-and-account-mode-response")

Interface：/api/v3/account/settings   
Adjustment：

* Account settings API adds UID and account mode response.

## [August 7, 2025] The depth channel push parameters have newly added the pseq parameter.[​](#august-7-2025-the-depth-channel-push-parameters-have-newly-added-the-pseq-parameter "Direct link to august-7-2025-the-depth-channel-push-parameters-have-newly-added-the-pseq-parameter")

Websocket: Depth Channel   
Adjustment:The depth channel push parameters have newly added the `pseq` parameter.

## [August 1, 2025] Add a new API for retrieving position ADL ranking[​](#august-1-2025-add-a-new-api-for-retrieving-position-adl-ranking "Direct link to august-1-2025-add-a-new-api-for-retrieving-position-adl-ranking")

Interface：/api/v3/position/adlRank  
Changes：

* Add a new API for retrieving position ADL ranking

## [July 31, 2025] Account Channel, Positions Channel Push Logic Optimization[​](#july-31-2025-account-channel-positions-channel-push-logic-optimization "Direct link to july-31-2025-account-channel-positions-channel-push-logic-optimization")

Websocket: Private Channels - Account Channel, Positions Channel  
Adjustment:

* Account Channel: Pushes the latest asset results; if there's a backlog of messages in the push queue, only the newest one will be pushed.
* Positions Channel: Order placement, modification, and cancellation operations for futures contracts will no longer be pushed.

## [July 30, 2025] Risk reserve API optimization[​](#july-30-2025-risk-reserve-api-optimization "Direct link to july-30-2025-risk-reserve-api-optimization")

Interface：/api/v3/market/risk-reserve  
Changes：

* Deprecate `totalBalance` and `type` fields; add `balance` field

## [July 30, 2025] New API for setting deposit accounts[​](#july-30-2025-new-api-for-setting-deposit-accounts "Direct link to july-30-2025-new-api-for-setting-deposit-accounts")

Interface：/api/v3/account/deposit-account  
Changes：

* New API for setting deposit accounts

## [July 30, 2025] New API for obtaining reserve certificates[​](#july-30-2025-new-api-for-obtaining-reserve-certificates "Direct link to july-30-2025-new-api-for-obtaining-reserve-certificates")

Interface：/api/v3/market/proof-of-reserves  
Changes：

* New API for obtaining reserve certificates

## [July 24, 2025] Position tier return unit changed to quete coin.[​](#july-24-2025-position-tier-return-unit-changed-to-quete-coin "Direct link to july-24-2025-position-tier-return-unit-changed-to-quete-coin")

Interface：/api/v3/market/position-tier
Changes：

* Position tier return unit changed to quete coin.

## [July 16, 2025] Add New Account Mode Switching API[​](#july-16-2025-add-new-account-mode-switching-api "Direct link to july-16-2025-add-new-account-mode-switching-api")

Interface：/api/v3/account/switch, /api/v3/account/upgrade
Adjustment:

* Add New Account Mode Switching API

## [July 9, 2025] The Get Risk Reserve interface has deprecated the totalBalance field.[​](#july-9-2025-the-get-risk-reserve-interface-has-deprecated-the-totalbalance-field "Direct link to july-9-2025-the-get-risk-reserve-interface-has-deprecated-the-totalbalance-field")

Interface：/api/v3/market/risk-reserve
Adjustment:

* The totalBalance field is deprecated in the response.

## [July 9, 2025] Unified Account Response/Push: New tradeSide Parameter Enumeration[​](#july-9-2025-unified-account-responsepush-new-tradeside-parameter-enumeration "Direct link to july-9-2025-unified-account-responsepush-new-tradeside-parameter-enumeration")

APIs：/api/v3/trade/fills;/api/v3/trade/order-info   
Channels: fill，order
Changes：

* Unified Account Response/Push: New tradeSide Parameter Enumeration

## [July 8, 2025] Add: Get sub-account unified account assets[​](#july-8-2025-add-get-sub-account-unified-account-assets "Direct link to july-8-2025-add-get-sub-account-unified-account-assets")

API: /api/v3/account/sub-unified-assets  
Changes:

* Add function to get sub-account unified account assets

## [July 8, 2025] Batch cancel orders supports partial success/failure[​](#july-8-2025-batch-cancel-orders-supports-partial-successfailure "Direct link to july-8-2025-batch-cancel-orders-supports-partial-successfailure")

APIs: RestAPI batch cancel orders & WebSocket batch cancel channel  
Changes:  
Batch cancel verification logic updated

* Current: If one order fails verification, all fail. Only success if all pass.
* Optimized: Each order verified separately. Supports partial success and failure.

## [July 8, 2025] REST Get Order Info API & WebSocket Order Channel add cancelReason enum[​](#july-8-2025-rest-get-order-info-api--websocket-order-channel-add-cancelreason-enum "Direct link to july-8-2025-rest-get-order-info-api--websocket-order-channel-add-cancelreason-enum")

APIs: RestAPI Get Order Info & WebSocket Order Channel  
Changes:

* Add cancelReason enum to the above API and channel

## [July 8, 2025] Add: Get trading fee API[​](#july-8-2025-add-get-trading-fee-api "Direct link to july-8-2025-add-get-trading-fee-api")

API: /api/v3/account/fee-rate  
Changes:

* Add function to get trading fees

## [July 2, 2025] Get the transfer records of Main-Sub account. API adjustment.[​](#july-2-2025-get-the-transfer-records-of-main-sub-account-api-adjustment "Direct link to july-2-2025-get-the-transfer-records-of-main-sub-account-api-adjustment")

Interface：/api/v3/account/sub-transfer-record
Adjustment:

* Response parameters now include oldTransferId.

## [July 02, 2025] WebSocket order, cancel, batch order, batch cancel channels launched[​](#july-02-2025-websocket-order-cancel-batch-order-batch-cancel-channels-launched "Direct link to july-02-2025-websocket-order-cancel-batch-order-batch-cancel-channels-launched")

Change: WebSocket order, cancel, batch order, batch cancel channels launched

## [July 1, 2025] Add New deposit and withdrawal APIs，add BGB deduction API.[​](#july-1-2025-add-new-deposit-and-withdrawal-apisadd-bgb-deduction-api "Direct link to july-1-2025-add-new-deposit-and-withdrawal-apisadd-bgb-deduction-api")

Interface：/api/v3/account/deposit-address, /api/v3/account/deposit-records, etc
Adjustment:

* Add New deposit and withdrawal APIs
* Add BGB deduction API.

## [June 25, 2025] Add CountDown Cancel All Interface[​](#june-25-2025-add-countdown-cancel-all-interface "Direct link to june-25-2025-add-countdown-cancel-all-interface")

Interface：/api/v3/trade/countdown-cancel-all   
Adjustment:

* Add set CountDown Cancel All interface

## [Jun 25, 2025] The order status will add the "new" status[​](#jun-25-2025-the-order-status-will-add-the-new-status "Direct link to jun-25-2025-the-order-status-will-add-the-new-status")

API Interface：Get Open Orders, Get Order History   
Websocket: Private Channel - Order Channel   
Change: "orderStatus" field will add new status "new", that means the order has been accepted by match engine

## [June 23,2025] Add affiliate-related APIs[​](#june-232025-add-affiliate-related-apis "Direct link to june-232025-add-affiliate-related-apis")

Interface：

* /api/broker/v1/agent/commission-distribution
* /api/broker/v1/agent/customerAccountAssetsList
* /api/broker/v1/agent/customerDepositList
* /api/broker/v1/agent/customer-kyc-result
* /api/broker/v1/agent/customerList
* /api/broker/v1/agent/customerTradeVolumnList
* /api/broker/v1/agent/customer-commissions

Changes：Add affiliate-related APIs

## [June 20,2025] New API: Fund Account Asset Query.[​](#june-202025-new-api-fund-account-asset-query "Direct link to june-202025-new-api-fund-account-asset-query")

Interface：/api/v3/account/funding-assets

Changes：New API: Fund Account Asset Query.

## [June 18,2025] Order Modification API & Batch Order Modification API Launched.[​](#june-182025-order-modification-api--batch-order-modification-api-launched "Direct link to june-182025-order-modification-api--batch-order-modification-api-launched")

Interface：/api/v3/trade/modify-order , /api/v3/trade/batch-modify-order

Changes：Order Modification API & Batch Order Modification API Launched.

## [June 17, 2025] Get transaction details and financial records. API adjustment.[​](#june-17-2025-get-transaction-details-and-financial-records-api-adjustment "Direct link to june-17-2025-get-transaction-details-and-financial-records-api-adjustment")

Interface：/api/v3/trade/fills

Changes：Add the `execPnl` field for trading profit and loss to the return values.

Interface：/api/v3/account/financial-records

Changes：Add the `other` type to the `category` enumeration in request parameters, and add a new request parameter `type` for account transaction types.

## [June 11, 2025] New Take-Profit and Stop-Loss Fields Added to Place Order Interface[​](#june-11-2025-new-take-profit-and-stop-loss-fields-added-to-place-order-interface "Direct link to june-11-2025-new-take-profit-and-stop-loss-fields-added-to-place-order-interface")

Interface：/api/v3/trade/place-order   
Adjustment:

* New take-profit and stop-loss fields added to request parameters.

## [June 09, 2025] Get Contract Information Adds Maximum Order Quantity Fields[​](#june-09-2025-get-contract-information-adds-maximum-order-quantity-fields "Direct link to june-09-2025-get-contract-information-adds-maximum-order-quantity-fields")

Interface：/api/v3/market/instruments   
Adjustment:

* Added `maxMarketOrderQty` field for the maximum quantity of a single market order.

## [June 05,2025] Added stpMode Field to Order Endpoints (Get Order Info, Get Open Orders, Get Order History)[​](#june-052025-added-stpmode-field-to-order-endpoints-get-order-info-get-open-orders-get-order-history "Direct link to june-052025-added-stpmode-field-to-order-endpoints-get-order-info-get-open-orders-get-order-history")

Interface: /api/v3/trade/order-info;/api/v3/trade/unfilled-orders;/api/v3/trade/history-orders;

Adjustment:The stpMode field has been added to the API response payloads for the following endpoints: Get Order Info; Get Open Orders; Get Order History;

## [May 14,2025] Adding new interface: Get Margin Loan[​](#may-142025-adding-new-interface-get-margin-loan "Direct link to may-142025-adding-new-interface-get-margin-loan")

Interface: /api/v3/market/margin-loans

Adjustment: Adding new interface to query interest rates for margin loans

## [May 14,2025] Adding new interface: Get Open Interest[​](#may-142025-adding-new-interface-get-open-interest "Direct link to may-142025-adding-new-interface-get-open-interest")

Interface: /api/v3/market/open-interest

Adjustment: Adding new interface to query the total number of unsettled or open futures

## [May 14,2025] Adjustment for Websocket Depth Channel[​](#may-142025-adjustment-for-websocket-depth-channel "Direct link to may-142025-adjustment-for-websocket-depth-channel")

Channel: Depth Channel

Adjustment: Adding `seq` in push data. It increments when the order book is updated and can be used to determine whether there is out-of-order packets.