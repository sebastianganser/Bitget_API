# Enumeration

## category[​](#category "Direct link to category")

* `SPOT` Spot
* `MARGIN` Spot Margin
* `USDT-FUTURES` USDT Futures
* `COIN-FUTURES` Coin-M Futures
* `USDC-FUTURES` USDC Futures

## side[​](#side "Direct link to side")

* `buy` Buy
* `sell` Sell

## orderType[​](#ordertype "Direct link to orderType")

* `limit` Limit
* `market` Market

## posSide[​](#posside "Direct link to posSide")

* `long` Long
* `short` Short

## timeInForce[​](#timeinforce "Direct link to timeInForce")

* `gtc` Good 'til canceled. *It remains active until it is either filled or manually canceled.*
* `post_only` Post only. *It will only be added to the order book as a maker.*
* `fok` Fill or Kill. *It must be fully executed immediately, or it is canceled entirely.*
* `ioc` Immediate or cancel. *It must be executed immediately, with any unfilled portion canceled*

## holdMode[​](#holdmode "Direct link to holdMode")

* `one_way_mode` One*way mode. \_Only single direction supported.*
* `hedge_mode` Hedge mode. *Both directions supported.*

## marginMode[​](#marginmode "Direct link to marginMode")

* `crossed` Crossed margin mode
* `isolated` Isolated margin mode

## reduceOnly[​](#reduceonly "Direct link to reduceOnly")

* `yes` Only position reduction supported.
* `no` Both reduction and increase are supported.

## execType[​](#exectype "Direct link to execType")

* `normal` Normal
* `offset` Offset
* `reduce` Forced reduction
* `liquidation` Liquidation
* `delivery` Delivery

## orderStatus[​](#orderstatus "Direct link to orderStatus")

* `live` Live
* `partially_filled` Partially filled
* `filled` Fully filled
* `cancelled` Cancelled

## tradeScope[​](#tradescope "Direct link to tradeScope")

* `taker` Taker, who executes an existing order, removing liquidity.
* `maker` Maker, who places a new order, adding liquidity.

## assetMode[​](#assetmode "Direct link to assetMode")

* `union` union-margin mode

## type (financial records)[​](#type-financial-records "Direct link to type (financial records)")

* `TRANSFER_IN` Fund transfer
* `TRANSFER_OUT` Fund transfer
* `ORDER_DEALT_FROZEN_OUT` Order dealt fund out
* `ORDER_DEALT_IN` Order dealt fund in
* `ORDER_PLF_FEE_OUT` handling fee deduction
* `EXCHANGE_SOURCE_TOKEN_USER_OUT` Redeem
* `EXCHANGE_TARGET_TOKEN_USER_IN` Redeem
* `OPEN_LONG` Open long
* `OPEN_SHORT` Open short
* `BUY_DEAL` Buy
* `SELL_DEAL` Sell
* `CLOSE_LONG` Close long
* `CLOSE_SHORT` Close short
* `FORCE_CLOSE_LONG` Forced reduction of long position
* `FORCE_CLOSE_SHORT` Forced reduction of short position
* `BURST_CLOSE_LONG` Liquidate long position
* `BURST_CLOSE_SHORT` Liquidate short position
* `OFFSET_REDUCE_CLOSE_LONG` Offset close long
* `OFFSET_REDUCE_CLOSE_SHORT` Offset close short
* `FORCE_BUY_SSM` Forced buy
* `FORCE_SELL_SSM` Forced sell
* `BURST_BUY_SSM` Liquidate buy
* `BURST_SELL_SSM` Liquidate sell
* `RISK_LIQ_USER_IN` User money in due to liquidation risk
* `RISK_LIQ_USER_OUT` User money out due to liquidation risk
* `INTEREST_SETTLEMENT_OUT` Interest deduction
* `CONTRACT_MAIN_SETTLE_FEE_USER_IN` Funding fee collection
* `CONTRACT_MAIN_SETTLE_FEE_USER_OUT` Funding Fee deduction
* `BORROW` Ins Loan borrow
* `RESERVE_TRANSFER_IN` Reserve transfer in
* `RESERVE_TRANSFER_OUT`Reserve transfer out
* `REPAYMENT` Ins Loan repayment
* `INTEREST_REPAYMENT` INTEREST REPAYMENT
* `LIQ_FUND_OUT`Liquidation fund out
* `LIQ_CONVERT_IN`Liquidation convert in
* `LIQ_CONVERT_OUT`Liquidation convert out
* `LIQ_TRANSFER_IN`Liquidation transfer in
* `LIQ_TRANSFER_OUT`Liquidation transfer out
* `LIQ_FUND_IN`Liquidation fund in
* `LIQ_FEE`Liquidation fee
* `LIQ_REPAYMENT` Liquidation repayment

## symbolType[​](#symboltype "Direct link to symbolType")

* `perpetual` Perpetual contract
* `delivery` Delivery contract

## status (instruments)[​](#status-instruments "Direct link to status (instruments)")

* `listed` Listed (not yet open)
* `online` Normal
* `limit_open` Order placement restricted
* `offline` Delisted / Under maintenance
* `restrictedAPI` API restricted

## deliveryStatus[​](#deliverystatus "Direct link to deliveryStatus")

* `delivery_config_period` Delivery configuration period
* `delivery_normal` Normal delivery period
* `delivery_before` Before delivery. No position opening is allowed 10 minutes
* `delivery_period` Delivery period. Opening, closing, and canceling orders is prohibited

## granularity[​](#granularity "Direct link to granularity")

* `1m` (1 minute)
* `3m` (3 minutes)
* `5m` (5 minutes)
* `15m` (15 minutes)
* `30m` (30 minutes)
* `1H` (1 hour)
* `4H` (4 hours)
* `6H` (6 hours)
* `12H` (12 hours)
* `1D` (1 day)
* `3D` (3 days)
* `1W` (1 week)
* `1M` (1 month)
* `6Hutc` (zero time zone 6-hour line)
* `12Hutc` (zero time zone 12-hour line)
* `1Dutc` (zero time zone 1-day line)
* `3Dutc` (zero time zone 3-day line)
* `1Wutc` (zero time zone 1-week line)
* `1Mutc` (zero time zone 1-month line)

## kLineType[​](#klinetype "Direct link to kLineType")

* `MARK` mark price K line
* `INDEX` index price K line
* `MARKET` Market price K line

## cancelReason[​](#cancelreason "Direct link to cancelReason")

* `normal_cancel` Normal cancellation
* `trade_too_many_times_cancel` Trading user restriction, only for special users
* `trade_count_too_small` Order cancelled due to too small tradable quantity
* `trade_too_many_times_cancel` Your order has been matched too many times and cannot continue to be filled
* `fok_not_full_cancel` FOK order not fully filled
* `ioc_not_full_cancel` IOC order not fully filled
* `post_only_fill_cancel` Post-only order filled immediately upon placement
* `self_trade_cancel` Self-trade cancellation
* `trade_max_deal_size_cancel` Your order has been filled too many times and cannot continue to be filled
* `tpsl_plan_cancel` Cancelled by conditional trigger
* `back_contract_cancel` Reverse position cancellation
* `delegated_risk_order_cancel` Risk control cancellation of delegated orders
* `trader_order_cancel` Copy trading order cancellation
* `delivery_order_cancel` Delivery cancellation
* `modify_limit_order` Limit order modification cancellation
* `slippage_cancel` Cancelled due to slippage ratio
* `adl_cancel` ADL cancellation
* `penetrate_cancel` Liquidation risk control
* `stp_cancel` Self-trade prevention cancellation
* `call_auction_cancel` Order cancelled due to call auction failure
* `limit_price_exceed_cancel` Order price exceeds limit range
* `burst_cancel` All your orders are automatically cancelled as your account enters liquidation/reduction state

## tradeSide[​](#tradeside "Direct link to tradeSide")

* `open_long` Open long
* `close_long` Close long
* `open_short` Open Short
* `close_short` Close short
* `reduce_close_long`: Liquidate partial long positions for hedge position mode
* `reduce_close_short`：Liquidate partial short positions for hedge position mode
* `burst_close_long`：Liquidate long positions for hedge position mode
* `burst_close_short`：Liquidate short positions for hedge position mode
* `offset_close_long`：Liquidate partial long positions for netting for hedge position mode
* `offset_close_short`：Liquidate partial short positions for netting for hedge position mode
* `delivery_close_long`：Delivery long positions for hedge position mode
* `delivery_close_short`：Delivery short positions for hedge position mode
* `dte_sys_adl_close_long`：ADL close long position for hedge position mode
* `dte_sys_adl_close_short`：ADL close short position for hedge position mode
* `buy_single`：Buy, one way postion mode
* `sell_single`：Sell, one way postion mode
* `reduce_buy_single`：Liquidate partial positions, buy, one way position mode
* `reduce_sell_single`：Liquidate partial positions, sell, one way position mode
* `burst_buy_single`：Liquidate short positions, buy, one way postion mode
* `burst_sell_single`：Liquidate partial positions, sell, one way position mode
* `delivery_sell_single`：Delivery sell, one way position mode
* `delivery_buy_single`：Delivery buy, one way position mode
* `dte_sys_adl_buy_in_single_side_mode`：ADL close position, buy, one way position mode
* `dte_sys_adl_sell_in_single_side_mode`：ADL close position, sell, one way position mode

## Tax type[​](#tax-type "Direct link to Tax type")

* `TRANSFER_IN` Transfer In
* `TRANSFER_OUT` Transfer Out
* `ORDER_DEALT_FROZEN_OUT` Order Dealt Deduction - User Out
* `ORDER_DEALT_IN` Order Dealt In - User In
* `ORDER_PLF_FEE_OUT` Exchange Token Fee Deduction - User Out
* `REPAY_SOURCE_USER_OUT` Repayment Out - User Out
* `REPAY_TARGET_USER_IN` Repayment In - User In
* `OPEN_LONG` Open Long Position Successfully
* `OPEN_SHORT` Open Short Position Successfully
* `BUY_DEAL` Buy Executed in Single-Side Mode
* `SELL_DEAL` Sell Executed in Single-Side Mode
* `CLOSE_LONG` Close Long
* `CLOSE_SHORT` Close Short
* `FORCE_CLOSE_LONG` Forced Reduce Long
* `FORCE_CLOSE_SHORT` Forced Reduce Short
* `BURST_CLOSE_LONG` Liquidation Close Long
* `BURST_CLOSE_SHORT` Liquidation Close Short
* `OFFSET_REDUCE_CLOSE_LONG` Net-Off Forced Reduce Long
* `OFFSET_REDUCE_CLOSE_SHORT` Net-Off Forced Reduce Short
* `FORCE_BUY_SSM` Forced Buy
* `FORCE_SELL_SSM` Forced Sell
* `BURST_BUY_SSM` Liquidation Buy
* `BURST_SELL_SSM` Liquidation Sell
* `RISK_LIQ_USER_IN` Risk Control - Debt Liquidation User In
* `RISK_LIQ_USER_OUT` Risk Control - Debt Liquidation User Out
* `INTEREST_SETTLEMENT_OUT` Interest Deduction - User Out
* `CONTRACT_MAIN_SETTLE_FEE_USER_IN` Cross Margin Funding Fee - User In
* `CONTRACT_MAIN_SETTLE_FEE_USER_OUT` Cross Margin Funding Fee - User Out
* `PAPTRADING_USER_IN` Demo Fund In - User In
* `PAPTRADING_USER_OUT` Demo Fund Out - User Out
* `RISK_TARGET_USER_IN` Forced Liquidation In - User In
* `RISK_SOURCE_USER_OUT` Forced Liquidation Out - User Out
* `ADL_CLOSE_LONG` ADL Close Long
* `ADL_CLOSE_SHORT` ADL Close Short
* `ADL_BUY_IN_SINGLE_SIDE_MODE` ADL Buy (Single-Side Mode)
* `ADL_SELL_IN_SINGLE_SIDE_MODE` ADL Sell (Single-Side Mode)
* `INS_LOAN_DISBURSE_USER_IN` Institutional Loan Disbursement - User In
* `INS_LOAN_DISBURSE_RESERVE_USER_OUT` Institutional Loan Disbursement to Reserve - User Out
* `INS_LOAN_REPAY_POOL_USER_OUT` Institutional Loan Repayment to Pool - User Out
* `INS_LOAN_REPAY_INTEREST_USER_OUT` Institutional Loan Repayment to Interest - User Out
* `INS_LOAN_REPAY_RESERVE_USER_IN` Institutional Loan Repayment to Reserve - User In
* `INS_LOAN_REPAY_FUND_USER_IN` Institutional Loan Repayment to Risk Fund - User In
* `INS_LOAN_EXCHANGE_USER_IN` Institutional Loan - Forced Liquidation Swap - User In
* `INS_LOAN_EXCHANGE_USER_OUT` Institutional Loan - Forced Liquidation Swap - User Out
* `INS_LOAN_TRANSFER_USER_IN` Institutional Loan - Forced Liquidation Transfer - User In
* `INS_LOAN_TRANSFER_USER_OUT` Institutional Loan - Forced Liquidation Transfer - User Out
* `INS_LOAN_REPAY_FEE_USER_OUT` Institutional Loan Repayment - Forced Liquidation Fee - User Out
* `INS_LOAN_REPAY_NON_MARGIN_USER_OUT` Institutional Loan Repayment - Forced Liquidation Recovery - User Out
* `DELIST_MARGIN_TOKEN_TARGET_USER_IN` Margin Delisted Token Redeem In - User In
* `DELIST_MARGIN_TOKEN_SOURCE_USER_OUT` Margin Delisted Token Redeem Out - User Out
* `SYSTEM_TRANSFER_OUT` System Transfer Out
* `SYSTEM_TRANSFER_IN` System Transfer In
* `SMALL_ASSET_SOURCE_TOKEN_USER_OUT` Small Asset Conversion - Source Token Out - User Out
* `SMALL_ASSET_TARGET_TOKEN_USER_IN` Small Asset Conversion - Target Token In - User In
* `FIXED_OPEN_LONG` Isolated Margin Open Long Position Successfully
* `FIXED_OPEN_SHORT` Isolated Margin Open Short Position Successfully
* `FIXED_BUY_DEAL` Isolated Margin Open Buy Executed (Single-Side)
* `FIXED_SELL_DEAL` Isolated Margin Open Sell Executed (Single-Side)
* `FIXED_BACK` Isolated Margin Return
* `FIXED_INCREASE_MARGIN` Increase Isolated Margin
* `FIXED_REDUCE_MARGIN` Decrease Isolated Margin
* `FIXED_SETTLE_FEE_USER_IN` Isolated Margin Funding Fee - User In
* `FIXED_SETTLE_FEE_USER_OUT` Isolated Margin Funding Fee - User Out
* `FIXED_LEVER_POS_IN` Isolated Margin Leverage Adjustment - Increase Margin
* `FIXED_REDUCE_ONLY_OFFSET_IN_SSM_LONG` Isolated Margin Single-Side Mode Long Reduce Only
* `FIXED_REDUCE_ONLY_OFFSET_IN_SSM_SHORT` Isolated Margin Single-Side Mode Short Reduce Only
* `FIXED_OFFSET_IN_SSM_LONG` Isolated Margin Reduce Long
* `FIXED_OFFSET_IN_SSM_SHORT` Isolated Margin Reduce Short
* `FIXED_ORDER_PLACE_FROZEN` Isolated Margin Order Placed Frozen
* `FIXED_ORDER_FROZEN_RETURN` Isolated Margin Unfreeze Return
* `FIXED_CLOSE_LONG` Isolated Margin Close Long
* `FIXED_CLOSE_SHORT` Isolated Margin Close Short
* `FIXED_FORCE_CLOSE_LONG` Isolated Margin Forced Reduce Long
* `FIXED_FORCE_CLOSE_SHORT` Isolated Margin Forced Reduce Short
* `FIXED_BURST_CLOSE_LONG` Isolated Margin Liquidation Close Long
* `FIXED_BURST_CLOSE_SHORT` Isolated Margin Liquidation Close Short
* `FIXED_ADL_CLOSE_LONG` Isolated Margin ADL Close Long
* `FIXED_ADL_CLOSE_SHORT` Isolated Margin ADL Close Short
* `FIXED_RISK_LIQ_USER_IN` Isolated Margin Risk Control - Debt Liquidation User In
* `FIXED_RISK_LIQ_USER_OUT` Isolated Margin Risk Control - Debt Liquidation User Out
* `FIXED_FORCE_BUY_SSM` Isolated Margin Forced Buy
* `FIXED_FORCE_SELL_SSM` Isolated Margin Forced Sell
* `FIXED_BURST_BUY_SSM` Isolated Margin Liquidation Buy
* `FIXED_BURST_SELL_SSM` Isolated Margin Liquidation Sell