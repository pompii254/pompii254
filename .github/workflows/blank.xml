//+------------------------------------------------------------------+
//| Script program start function                                      |
//+------------------------------------------------------------------+
int OnInit()
{
  return(INIT_SUCCEEDED);
}

//+------------------------------------------------------------------+
//| Deinit function                                                   |
//+------------------------------------------------------------------+
void OnDeinit(const int reason)
{
  ObjectDelete(_Symbol);
}

//+------------------------------------------------------------------+
//| Tick function                                                     |
//+------------------------------------------------------------------+
void OnTick()
{
  double stake = 5.0; // Initial stake
  double targetProfit = 1000.0; // Target profit
  double lossLimit = 500.0; // Loss limit
  double randomIndex = MathRand() % 100; // Random index (0-99)
  double syntheticIndex = MathRand() % 100; // Synthetic index (0-99)
  double multiplier = 1.2; // Multiplier
  int digitOver = 7; // Digit over value

  // Calculate profit/loss
  double profit = 0.0;
  if (randomIndex > 60 && syntheticIndex > 50) {
    profit = stake * 2.0; // Win condition
  } else if (randomIndex < 40 && syntheticIndex < 30) {
    profit = -stake * 1.5; // Loss condition
  }

  // Apply multiplier and digit over
  if (profit > 0) {
    profit *= multiplier;
    if (MathAbs(profit) > digitOver) {
      profit = digitOver;
    }
  }

  // Check for stop-loss
  if (profit < -lossLimit) {
    profit = -lossLimit; // Stop-loss triggered
  }

  // Print result
  printf("Profit: %.2f", profit);
}

//+------------------------------------------------------------------+
//| Script deinit function                                            |
//+------------------------------------------------------------------+
void OnDeinit(const int reason)
{
  ObjectDelete(_Symbol);
}
