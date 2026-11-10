# Normalising Growth

How Pot Tracker measures a pot's growth so that money paid in, taken out or moved between pots never counts as growth,
and pots of different sizes and ages compare on the same terms.

## Context
* [Pot Tracker](../../../PRODUCT.md) - the root index for this repo
* [compare-growth](../use-cases/compare-growth/USE-CASE.md) - the use case this serves
* [Pots, Providers and Money Moved](pots-and-providers.md) - the money moved that is taken out of growth

## 1 The Growth Index

**Each line on the chart is a growth index: what one pound in the pot at the start of the period has become.** Every
line starts at 1 (the chart's origin is the start of the period, at 1). A pot that grew by a fifth stands at 1.2; one
that lost a tenth stands at 0.9.

The index is not the pot's value. A pot's value goes up when money is paid in; its index does not. That is the whole
point: the saver sees how the *investments* did, not how much they saved.

## 2 Working It Out

The index moves only between valuations, by the return over that stretch with the money moved taken out:

```
return  = (value at the end − value at the start − money moved in, net) / (value at the start + money moved in, net)
index   = index before × (1 + return)
```

Money moved is counted at the start of the stretch it falls in. This is a time-weighted return: each stretch is
weighted the same, whatever the pot held then, so paying a large sum in before a good month does not flatter the pot.

**An example.** A pot holds £10,000.

| When | Value | Money moved | Return | Index |
|---|---|---|---|---|
| Start | £10,000 | | | 1.000 |
| End of month 1 | £10,500 | | 5% | 1.050 |
| Start of month 2 | £15,500 | £5,000 paid in | | 1.050 |
| End of month 2 | £15,810 | | 2% | 1.071 |

The pot's value rose by 58%; its index by 7.1%, which is what its investments did.

Because the money moved is taken out where it happens, **a line stays smooth when money moves**: there is no step up
when a payment arrives, nor down when a transfer leaves. The growth chart marks no transfers, since there is nothing on
a line to mark; the money moved has a chart of its own beneath it (§7).

## 3 All Pots Together

**The line of all pots together is the index of every pot the saver has with a history, as if they were one pot.**
Money moved between two of the saver's pots leaves one and arrives at the other, so it cancels out; only money paid in
from outside, or taken out to outside, is taken out of growth. Pots that are hidden on the chart still count towards it.

## 4 A Pot That Starts Late

A pot whose history starts after the period does (one added recently, or one whose platform gives no earlier history)
has no index before its history starts. **Its line starts where its history does, at the value the line of all pots
together has reached then**, not at 1. From there it moves by its own returns.

So a pot that starts late is compared on the same terms as the pots that were already growing: if it then does better
than the rest, its line ends above theirs; if worse, below. Starting it at 1 would put it below every pot that had grown
before it existed, and say nothing true.

Its yearly rate beside the chart (§5) is over the time it has, from its start to the end of the period.

## 5 The Yearly Rate

Beside the chart, each pot's growth over the period is given only as a yearly rate, so pots with histories of different
lengths, and periods of different lengths, compare:

```
yearly rate = (index at the end / index at the start) ^ (1 / years) − 1
```

## 6 What Has No Index

* **A pot added by hand without a history** has only today's value, so there is nothing to work a return from.
* **A promised-income pension** does not grow with investments; what it promises is set by the scheme's rules.

Neither is shown on the chart, and the saver is told why ([compare-growth](../use-cases/compare-growth/USE-CASE.md)
2b).

A pension found by the search does have an index, but only from when it was found
([Finding Pensions](finding-pensions.md) §4): before that, it is a pot that starts late (§4).

## 7 What A Move Has Been Worth

The money moved chart, beneath the growth chart, has a bar for each movement: above the line for money into a pot,
below it for money out, as large as the amount. Money moved between two of the saver's pots is two bars, one out of the
pot it left and one into the pot it went to.

**What an amount moved into a pot at one time is worth at a later time is the amount grown by that pot's index:**

```
worth in a pot  = amount × (index at the end / index when it moved)
```

"The end" is the end of the chart's period. A bar chosen answers one question, depending on which way it points:

| Bar | 100% is | The percentage shown is | So |
|---|---|---|---|
| **Out of a pot, into another** | What the amount would be worth had it stayed in the pot it left | What it is worth in the pot it went to | Over 100%: the move did better than staying |
| **Into a pot** | What the amount is worth in the pot it went to | The least and the most it would be worth in each of the saver's other pots, naming each | Where the money could have done better or worse |

**Money taken out to the bank has no percentage**: it has left the saver's pots, so there is nothing it is worth in
one. Its bar shows only the amount.

**An example.** £5,000 moves from pot A to pot B when A's index is 1.10 and B's is 1.05. At the end, A's is 1.21 and
B's is 1.26.

* Had it stayed in A: £5,000 × 1.21 / 1.10 = £5,500. That is 100%.
* In B: £5,000 × 1.26 / 1.05 = £6,000. The out bar on A shows **109%**.
* The in bar on B shows £6,000 as 100%, and, if pot C's index went from 1.00 to 1.08, C as the least: £5,400, **90%**;
  and A, £5,500, **92%**, as the most, if no other pot did better.

A pot with no index at the time the money moved (§6, or §4 before its history starts) cannot be compared: it is left out
of the least and most, and a move out of it has no percentage.
