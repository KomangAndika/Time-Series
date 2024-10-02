Here is a small list of places to begin looking for strategy ideas:

- **Social Science Research Network** - [www.ssrn.com](http://www.ssrn.com/)
- **arXiv Quantitative Finance** - [arxiv.org/archive/q-fin](http://arxiv.org/archive/q-fin)
- **Seeking Alpha** - [www.seekingalpha.com](http://www.seekingalpha.com/)
- **Elite Trader** - [www.elitetrader.com](http://www.elitetrader.com/)
- **Nuclear Phynance** - [www.nuclearphynance.com](http://www.nuclearphynance.com/)
- **Quantivity** - [quantivity.wordpress.com](http://quantivity.wordpress.com/)

Many of the strategies you will look at will fall into the categories of _mean-reversion_ and _trend-following/momentum_

A mean-reverting strategy is one that attempts to exploit the fact that a long-term mean on a "price series" (such as the spread between two correlated assets) exists and that short term deviations from this mean will eventually revert. A momentum strategy attempts to exploit both investor psychology and big fund structure by "hitching a ride" on a market trend, which can gather momentum in one direction, and follow the trend until it reverses.

Another hugely important aspect of quantitative trading is the _frequency_ of the trading strategy. _Low frequency trading_ (LFT) generally refers to any strategy which holds assets longer than a trading day. Correspondingly, _high frequency trading_ (HFT) generally refers to a strategy which holds assets intraday. _Ultra-high frequency trading_ (UHFT) refers to strategies that hold assets on the order of seconds and milliseconds. As a retail practitioner HFT and UHFT are certainly possible, but only with detailed knowledge of the trading "technology stack" and _order book dynamics_. We won't discuss these aspects to any great extent in this introductory article.

 We will discuss the common types of bias including _look-ahead bias_, _survivorship bias_ and _optimisation bias_ (also known as "data-snooping" bias). Other areas of importance within backtesting include availability and cleanliness of historical data, factoring in realistic transaction costs and deciding upon a robust backtesting platform. We'll discuss transaction costs further in the Execution Systems section below.

The main concerns with historical data include accuracy/cleanliness, survivorship bias and adjustment for _corporate actions_ such as dividends and stock splits:

- **Accuracy** pertains to the overall quality of the data - whether it contains any errors. Errors can sometimes be easy to identify, such as with a _spike filter_, which will pick out incorrect "spikes" in time series data and correct for them. At other times they can be very difficult to spot. It is often necessary to have two or more providers and then check all of their data against each other.
- **Survivorship bias** is often a "feature" of free or cheap datasets. A dataset with survivorship bias means that it does not contain assets which are no longer trading. In the case of equities this means delisted/bankrupt stocks. This bias means that any stock trading strategy tested on such a dataset will likely perform better than in the "real world" as the historical "winners" have already been preselected.
- **Corporate actions** include "logistical" activities carried out by the company that usually cause a step-function change in the raw price, that should not be included in the calculation of _returns_ of the price. Adjustments for dividends and stock splits are the common culprits. A process known as _back adjustment_ is necessary to be carried out at each one of these actions. One must be very careful not to confuse a stock split with a true returns adjustment. Many a trader has been caught out by a corporate action!

