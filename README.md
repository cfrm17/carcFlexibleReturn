# Capped Accumulated Return Call Valuation with Flexible Return

A Monte Carlo (Monte Carlo, MC, and Quasi Monte Carlo, QMC) pricing model is presented for a new variation on the product named capped-accumulated-return-call (CARC): CARC with pick and choose the return period. User specifies the dates where equity returns are to be calculated and then used in the final payoff.

Let   be a stock,   be the price process of the stock, and   be a set of reset dates and   be a payoff settlement date.  The simple CARC with underlying  is a European type derivative security whose matured payoff at the settlement date is given by

	 	(1)

where   is the global floor of the return rate, N is the notional principal, and   is accumulated return and defined as

	 	(2)

where   is the capped return-rate for each period described as follows:  Define the actual period return-rate as
				 ,	(3)

Then we define

	 ,	(4)

where c is the cap.

The notional N may or may not be added to the payoff.

The new attribute RETURN_CALCULATION_DATE_FILE specifies the dates where the capped-returns are to be calculated and then used for the computation of the payoff. Let   an increasing subsequence of the sequence . The payoff  (with notional) of CARC with pick and choose return period feature is then: 

 , 

where    .

Let t be the current value date, then the current value of CARC with pick and choose return feature (with notional) can be written
 	   					
where   is the discounting factor at the value date.  The above formula is in a world that is risk-neutral. The governing price dynamics of the underlying asset in the risk-neutral world  is

	 	(7)

where   is the short rate, q is the dividend yield of the asset,   is the volatility of the asset price, and   is the Wiener process.  All these parameters are assumed deterministic. The above dynamics is used to simulate the returns at reset dates.

Let   be the option value,   be the volatility of the underlying asset (SPX), and C the USD discount curve (ref. https://finpricing.com/lib/IrInflationCurve.html  denotes parallel shift by 10 bps). The formulas used are: 

  

and 

 . 

Let  be the option value when the underlying price is  (in our case SPX-IC), and let .  The formula used is:


 
