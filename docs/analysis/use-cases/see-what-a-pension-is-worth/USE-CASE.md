# See What A Pension Is Worth

**Actor:** a saver, most often the [near-retirement planner](../../user-personas/near-retirement-planner.md); any of them
may
**Scope:** does not cover how a pot has grown in the past ([compare-growth](../compare-growth/USE-CASE.md)), or moving
money between pots ([transfer-between-pots](../transfer-between-pots/USE-CASE.md)).

## Context
* [Pot Tracker](../../../../PRODUCT.md) - what the product is
* [Projecting A Retirement Value](../../domain/projecting-a-retirement-value.md) - what a projection assumes, and why it
  is only ever an illustration

## 1 Goal

The saver knows what a pension is worth now, and what it might give them when they retire, on assumptions they can see
and change.

## 2 Trigger

The saver wants to know whether a pension, or all of them, will be enough.

## 3 Preconditions

* The saver is signed in ([sign-in](../sign-in/USE-CASE.md)).
* The saver has at least one pension among their pots ([find-my-pensions](../find-my-pensions/USE-CASE.md),
  [add-an-investment-portfolio](../add-an-investment-portfolio/USE-CASE.md)).

## 4 Main Success Scenario

1. The saver chooses a pension from their pots.
2. The saver sees what it is worth now: its value, when that was last brought up to date, and what has been paid into it
   over the past year.
3. The saver sees what it might be worth at the age they mean to retire: as a pot, and as the yearly income it might
   buy, both in today's money, with the assumptions behind them beside them.
4. The saver changes an assumption that is theirs to make, their retirement age or what they pay in each month, and sees
   the projection change as they do.
5. The saver keeps the assumptions they chose, and sees them used for this pension from now on.

## 5 Postconditions

* The saver's assumptions are kept, and used wherever this pension is projected.
* Nothing about the pension itself was changed: a projection changes no contribution or retirement date at the
  provider.

## 6 Extensions

1a. The saver chooses to see all their pensions together: they see the total now, and what all of them might give at
retirement, each pension's share shown. Go to 4, where an assumption changed applies to every pension.

3a. The pension is a promised income, not a pot of money: the saver sees the yearly income it promises from the
scheme's own retirement age, and what it would be worth if transferred, where the scheme gives that. There is no growth
to assume. Go to 5.

3b. The pension has no value yet ([find-my-pensions](../find-my-pensions/USE-CASE.md) 5b): the saver is told no
projection can be made until it has one, and when it is expected.

3c. The saver asks to see a lower and a higher projection: they see the projection on lower and higher growth beside
the one shown, the range it might fall in.

4a. The saver gives a retirement age earlier than a pension can be taken: they are told the earliest age it can, and the
projection uses that.

4b. The saver changes their mind: they put the assumptions back as they were, and nothing is kept.

## 7 Open Questions (not resolved by this use case)

* Whether the State Pension is included in the total, which the pension-finding service can find
  ([find-my-pensions](../find-my-pensions/USE-CASE.md) §7).
* Whether the saver can change the growth rate assumed, or only choose lower and higher.

## 8 Gate

The end-to-end test a UI slice delivering this use case must pass. Its walkthrough, once drawn, is
`walkthroughs/see-what-a-pension-is-worth`.

* **Main scenario:** choose a pension; see its value, when it was updated and the past year's payments; see its
  projection as a pot and as an income, in today's money, with the assumptions beside it; change the retirement age
  and see it change; keep it, and see it kept on returning.
* **1a:** choose all pensions; see the total and each pension's share; change the retirement age; see every pension's
  projection change.
* **3a:** choose a promised-income pension; see its income from the scheme's age, and its transfer value.
* **3b:** choose a pension with no value; be told why there is no projection.
* **3c:** ask for lower and higher; see the range.
* **4a:** give a retirement age of 50; be told the earliest is 57, and see it used.
* **4b:** change an assumption and put it back; see nothing kept.
