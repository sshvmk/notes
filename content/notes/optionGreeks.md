---
title: Brief intro to Options Greeks
date: 2024-05-16
tags:
  - stock
enableToc: true
---

I am copying content from an old tweet of mine. If you prefer reading tweet, [click here](https://x.com/drrstock/status/1675197046599610368)

Markets influence the greeks, greeks then in turn influence price of an option. To make situation more complex greeks affect each other as well.

Main Greeks are :

### 1. Delta

It captures the effect of directional movement of market on option's premium.
Say you have calculated that the underlying stock/index will move up by a certain percentage but how do you know what will be the value of options then ? Delta comes in handy here. \
 Delta for Call options : [0, 1] and for Put options : [-1, 0]
What does this even mean ? Continuing with the previous example. You make position in CE and strike price you choose has a delta of say 0.6, it means that if underlying is up by 100, your option price will go up by 60 \
 Similarly, if you make position in PE of a strike price which has delta -0.4 If market falls 100 points your PE price will go up by 40 & if market goes up by 100 your PE will go down by -40.
Keep in mind, these are theoretical calculations & not exactly how it works in real life. \
 You can check greeks value on any of the software of your choosing. \
 | option type | approx delta value (CE) | approx delta value (PE) |
|-|-|-|
| Deep ITM | +0.8 to +1 | -0.8 to -1 |
| Slighty ITM | +0.6 to +1 | -0.6 to -1 |
| ATM | +0.45 to +0.55 | -0.45 to -0.55 |
| Slightly OTM | +0.45 to +0.3 | -0.45 to -0.3 |
| Deep OTM | +0.3 to 0 | -0.3 to 0 |

### 2. Gamma

Well if delta changes so does my price. So how can i estimate the likely change in delta ? Answer is Gamma. It is expressed as deltas gained or lost per 1 point change in underlying - with the delta increasing by the amount of gamma when underlying rises & vice versa. \
Gamma is always a positive number for both Call and Put Option. Therefore when the trader is long options (call or put) trader is considered 'Long gamma' and when he is short options (call or puts) he is considered 'Short Gamma'. \
Gamma is really helpful in risk estimation. I would suggest anyone to read this in more detail to understand how to manage risk with change in gamma.

> Note : _Gamma is highest for ATM options and low for ITM and OTM options._

### 3. Theta

The Theta or time decay factor is the rate at which an option loses value as time passes.
Every beginner buys an option and even if the market was at same levels option's value decreases and he/she thinks how am I seeing losses here ? Well say hello to Theta. \
Nifty is 19000 suppose, what is the probability that it will move 200 points & 19200 CE will become ITM ? Depends how much time is left in expiry. If 30 days left, chances are high. If only 10 days left, it is still possible but less probable. Nearer the expiry, lesser the chance. \
Option premium = intrinsic value + time value.
This time value is the value that gets eroded.

> OTM options have no intrinsic value. And if options stays OTM till expiry thanks to theta it becomes 0.
> Rate of drop in premium due to theta is higher when close to expiry

### 4. Vega

Vega of an option measures the rate of change of option’s value (premium) with every percentage change in volatility. We are talking about implied volatility here. \
Other types are historical volatility & forecasted volatility. But Implied Volatility (IV) is more valued. \
When volatility increases, the option premiums have a higher chance to expire in the money.
So when volatility increases, premiums get much higher. But the question is ‘By how much ?’. This is exactly what the Vega tells us. \
The effect of increase in volatility is maximum when there are more days to expiry – this means if you are at the start of series, and the volatility is high then you know premiums are plum.
