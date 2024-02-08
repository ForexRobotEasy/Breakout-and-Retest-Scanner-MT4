# Breakout and Retest Scanner MT4

This code is a sample implementation of the Breakout and Retest Scanner strategy in MetaTrader 4 (MT4). It is developed by the Forex Robot Easy Team and can be used to identify and trade breakouts and retests in the forex market.

## How it Works

The code utilizes the Trade and BreakoutAndRetest libraries to execute trades and analyze market conditions, respectively. Here's a breakdown of how the strategy works:

1. Include necessary libraries and indicators:
```mql5
#include <Trade\Trade.mqh>
#include <Indicators\BreakoutAndRetest.mqh>
```

2. Define global variables:
```mql5
CTrade trade;
CBreakoutAndRetest breakoutAndRetest;
```

3. Initialize the EA:
```mql5
int OnInit()
{
    trade.SetExpertMagicNumber(123456); // Set the expert magic number

    breakoutAndRetest.Init(Symbol(), Period());

    return(INIT_SUCCEEDED);
}
```

4. Execute the EA on every tick:
```mql5
void OnTick()
{
    if(breakoutAndRetest.CheckBreakout()) // Check for breakout
    {
        trade.Buy(Symbol(), 0.1, 0, 0, 0); // Open a buy position
        trade.Sell(Symbol(), 0.1, 0, 0, 0); // Open a sell position
    }
    else if(breakoutAndRetest.CheckRetest()) // Check for retest
    {
        trade.CloseAll(); // Close all positions
    }
}
```

The EA checks for breakout signals using the `CheckBreakout()` function from the `breakoutAndRetest` instance. If a breakout is detected, it opens both a buy and sell position using the `Buy()` and `Sell()` functions from the `trade` instance.

Similarly, if a retest is detected using the `CheckRetest()` function, it closes all open positions using the `CloseAll()` function.

## Product Description

The Breakout and Retest Scanner MT4 is a powerful trading tool developed by the Forex Robot Easy Team. It is designed to identify breakouts and retests in the forex market, allowing traders to capitalize on potential trading opportunities.

This code provides a sample implementation of the strategy and can be used as a reference for traders who want to develop their own breakout and retest scanning tools.

Please note that ForexRobotEasy is not the official developer of this product. We are showcasing a sample code that can work as described in the product. To find the official developer of this product, please use MQL5.

For detailed reviews and trading results of this product, please visit [https://forexroboteasy.com/forex-robot-review/breakout-retest-scanner-mt4-review-avoid-false-breakouts/](https://forexroboteasy.com/forex-robot-review/breakout-retest-scanner-mt4-review-avoid-false-breakouts/).
