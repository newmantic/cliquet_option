# cliquet_option

A Cliquet Option, also known as a Ratchet Option, is an exotic option that features periodic resets of the strike price to the current price of the underlying asset. At each reset date, the option effectively locks in gains if the underlying asset has moved favorably, making it a structured product that combines elements of both a series of forward-starting options and traditional options.


Underlying Asset (S): The asset on which the option is based (e.g., a stock, index).
Initial Strike Price (K_0): The strike price set at the inception of the option.
Reset Dates: The dates at which the strike price is reset to the current price of the underlying asset. These could be annual, semi-annual, quarterly, etc.
Cap (C): The maximum payoff allowed for each reset period (optional).
Floor (F): The minimum payoff guaranteed for each reset period (optional).

Call Option: Gives the holder the right to buy the underlying asset at the strike price.
Put Option: Gives the holder the right to sell the underlying asset at the strike price.
Final Payoff: The sum of the payoffs accumulated at each reset date.


Call Option Payoff at Each Reset (i):
At each reset date t_i, the strike price is updated to the current price of the underlying asset S_{t_i}.
The payoff for a call option at reset t_i is:
Payoff_i = max(S_{t_{i+1}} - S_{t_i}, 0)
Where:
S_{t_{i+1}} is the price of the underlying asset at the next reset date.
S_{t_i} is the price of the underlying asset at the current reset date.

Put Option Payoff at Each Reset (i):
For a put option, the payoff at reset t_i is:
Payoff_i = max(S_{t_i} - S_{t_{i+1}}, 0)

Cap and Floor:
If there is a cap C, the payoff at each reset is limited to a maximum value:
Payoff_i = min(Payoff_i, C)
If there is a floor F, the payoff at each reset has a minimum value:
Payoff_i = max(Payoff_i, F)

Cumulative Payoff:
The final payoff of the Cliquet option is the sum of the payoffs at all reset dates:
Total Payoff = sum_{i=1}^{n} Payoff_i
Where n is the total number of reset periods.
