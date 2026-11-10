# Projecting A Retirement Value

What a pension might be worth when the saver retires, how Pot Tracker works it out, and why it is only ever an
illustration.

## Context
* [Pot Tracker](../../../PRODUCT.md) - the root index for this repo
* [see-what-a-pension-is-worth](../use-cases/see-what-a-pension-is-worth/USE-CASE.md) - the use case this serves
* [Pots, Providers and Money Moved](pots-and-providers.md) - the kinds of pension

## 1 An Illustration, Not A Promise

**A projection is what a pension might be worth if the assumptions hold, and they won't exactly.** It is always shown
with its assumptions beside it, always in today's money, and never as a promise or as advice. Pot Tracker projects every
pension on the same assumptions, so the projections add up, unlike each provider's own on its own.

## 2 The Assumptions

| Assumption | Whose | Default |
|---|---|---|
| Retirement age | The saver's | 67, the State Pension age for most savers |
| What is paid in each month | The saver's | What was paid in over the past year, divided by twelve; nothing for a pension no longer paid into |
| Growth each year, after charges | Pot Tracker's | 4%; lower 1% and higher 7% (§4) |
| Inflation each year | Pot Tracker's | 2.5% |
| Income a pot buys each year | Pot Tracker's | 5% of the pot at retirement, for life |

The saver changes their own two; Pot Tracker's are shown but not changed. **What the saver chooses changes nothing at
the provider**: a higher monthly payment in a projection pays nothing in.

## 3 Working It Out

Month by month from today to the retirement age, the pot grows at the monthly growth rate, and the monthly payment is
added. The result is brought back to today's money by inflation over the same time. The yearly income is the income
rate of that.

```
months      = (retirement age − age today) × 12
pot then    = value today × (1 + g)^months + payment × ((1 + g)^months − 1) / g        where g is the monthly growth
today's £   = pot then / (1 + inflation)^(months / 12)
income      = today's £ × income rate
```

## 4 Lower And Higher

The lower and higher projections use the same assumptions but growth. Together they are the range a projection might
fall in. They are shown beside the middle one, never instead of it.

## 5 Ages And Kinds

* **The earliest a pension can be taken is 57.** A retirement age before that is not refused; it is moved to 57, and
  the saver is told.
* **A promised-income pension is not projected.** It promises a yearly income from the scheme's own retirement age,
  which the scheme states; Pot Tracker shows that, in today's money where the scheme says how it rises, and the value
  the scheme would transfer it at, where it gives one.
* **A pension with no value yet** has no projection until it has one.

## 6 All Pensions Together

The total is the sum of each pension's projection, each on the same assumptions. A retirement age chosen for all
pensions together applies to each.
