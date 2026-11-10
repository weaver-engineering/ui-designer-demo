# Compare Growth

**Actor:** a saver, most often the [hands-on investor](../../user-personas/hands-on-investor.md); any of them may
**Scope:** does not cover what a pension might be worth in future
([see-what-a-pension-is-worth](../see-what-a-pension-is-worth/USE-CASE.md)), or moving money between pots
([transfer-between-pots](../transfer-between-pots/USE-CASE.md)).

## Context
* [Pot Tracker](../../../../PRODUCT.md) - what the product is
* [Normalising Growth](../../domain/normalising-growth.md) - how growth is measured so money moved in and out does not
  count as growth, and how what a move has been worth is worked out

## 1 Goal

The saver sees how each of their pots, and all of them together, has really grown, on the same terms, with the money
they moved in and out taken out of it; and sees whether the money they moved went to the right place.

## 2 Trigger

The saver wants to know which of their pots is doing well, and whether moving money between them has paid off.

## 3 Preconditions

* The saver is signed in ([sign-in](../sign-in/USE-CASE.md)).
* The saver has at least one pot with a history of its value
  ([add-an-investment-portfolio](../add-an-investment-portfolio/USE-CASE.md),
  [find-my-pensions](../find-my-pensions/USE-CASE.md)).

## 4 Main Success Scenario

1. The saver asks to compare growth.
2. The saver sees a chart of each pot's growth over the past year, and of all of them together, each as what one pound
   at the start of the period has become, so every line starts at 1. Money paid in, taken out or moved between pots
   does not count as growth, so a line moves only as its investments do, and stays smooth when money moves.
3. Below it, over the same time, the saver sees a chart of the money moved: a bar for each time money went into a pot,
   above the line, and for each time money left one, below it, each as large as the amount and marked as its pot's
   line is. Money moved from one pot to another is two bars: out of the one, into the other.
4. The saver chooses the period to compare over: one, three or five years, or since their first pot began. Both charts
   show it.
5. The saver chooses which pots are shown, on both charts.
6. The saver points at a time on either chart, and sees each pot's growth to then.
7. The saver chooses a bar of money that left a pot for another of their pots, and sees what the move has been worth: as
   a percentage of what the money would be worth now had it stayed in the pot it left, so more than 100% means it did
   better where it went. Money taken out to the saver's bank has no percentage: it is no longer in a pot to be worth
   anything.
8. Beside the charts, the saver sees each pot's yearly rate of growth over the period, with all of them together
   last.

## 5 Postconditions

* The period and pots chosen are kept, and shown the next time the saver compares growth.
* Nothing is changed: comparing growth only reads.

## 6 Extensions

2a. A pot's history starts after the period does: its line starts where its history does, at the value the line of all
pots together has reached by then, so it is compared from there on the same terms as the pots that were already
growing. Its yearly rate beside the chart is over the time it has.

2b. A pot has no history ([add-an-investment-portfolio](../add-an-investment-portfolio/USE-CASE.md) 2a), or is a
promised-income pension, which does not grow with investments: it is not shown on either chart, and the saver is told
why.

7a. The saver chooses a bar of money that went into a pot: they see what it is worth now in that pot, as 100%, and
beside it the least and the most it would be worth had it gone into another of their pots instead, each as a
percentage of that and naming the pot.

7b. The pot the money left, or another pot it is compared with, had no history at the time: the saver is told what
cannot be compared, and why. A move from outside compared with no other pot shows only its 100%.

## 7 Open Questions (not resolved by this use case)

* Whether a pot can be compared against a market index.
* Whether charges are shown as well as growth after charges.
* Whether the least and most a move into a pot might have been worth (7a) count pots it could not have gone into, such
  as an ISA beyond the year's allowance.

## 8 Gate

The end-to-end test a UI slice delivering this use case must pass. Its walkthrough, once drawn, is
`walkthroughs/compare-growth`.

* **Main scenario:** ask to compare growth; see every pot's line and the total's, all starting at 1, over a year, and
  below it the money moved, in above the line and out below; choose five years and see both charts show it; hide one
  pot and see it gone from both; point at a time and see each pot's growth to then; choose a transfer's bar out of a
  pot and see what it has been worth as a percentage; see each pot's yearly rate beside the charts.
* **Smooth through money moved:** with a transfer between two pots in the period, see neither pot's line jump where it
  happened, and see it as one bar out of the one and one into the other.
* **2a:** compare over five years with a pot two years old; see its line start two years in, on the line of all pots
  together.
* **2b:** have a pot added by hand and a promised-income pension; see neither shown, and why.
* **7a:** choose a payment into an ISA; see 100%, and the least and most it would be worth in another pot, naming each.
* **7b:** choose a move from a pot with no history then; be told it cannot be compared.
