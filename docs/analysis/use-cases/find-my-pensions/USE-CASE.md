# Find My Pensions

**Actor:** a saver: any of the [mid-career saver](../../user-personas/mid-career-saver.md), the
[near-retirement planner](../../user-personas/near-retirement-planner.md) or the
[hands-on investor](../../user-personas/hands-on-investor.md)
**Scope:** does not cover claiming a pension a provider is not sure is the saver's
([claim-a-possible-match](../claim-a-possible-match/USE-CASE.md)), or adding pots that are not pensions
([add-an-investment-portfolio](../add-an-investment-portfolio/USE-CASE.md)), or what a pension found is worth at
retirement ([see-what-a-pension-is-worth](../see-what-a-pension-is-worth/USE-CASE.md)).

## Context
* [Pot Tracker](../../../../PRODUCT.md) - what the product is
* [Finding Pensions](../../domain/finding-pensions.md) - the pension-finding service, and what it can and cannot say

## 1 Goal

Every pension the saver has, including those they have lost track of, is one of their pots in Pot Tracker.

## 2 Trigger

The saver has just signed up ([sign-up](../sign-up/USE-CASE.md) 5), or thinks there may be a pension they have not
found yet.

## 3 Preconditions

* The saver is signed in ([sign-in](../sign-in/USE-CASE.md)).

## 4 Main Success Scenario

1. The saver asks to find their pensions, and is told what will happen: who will be searched, what is shared, and
   that answers can take a few days to arrive.
2. The saver proves who they are to the pension-finding service.
3. The saver agrees that the service may search for their pensions, and that Pot Tracker may receive what it finds.
4. The search starts, and the saver is told it has.
5. As each provider answers, its pension is added to the saver's pots: the provider, the employer it came from, whether
   it is a pot of money or a promised income, and its value.
6. The saver is told when the search has finished, and how many pensions were found.

## 5 Postconditions

* Each pension found is one of the saver's pots, marked as found by the search.
* The saver's consent is recorded, with when it was given and when it ends, which is a year later.

## 6 Extensions

1a. The saver has searched before, and their consent has not ended: they are not asked to prove who they are or to
agree again. Go to 4.

2a. The saver cannot prove who they are: they are told the search cannot start, and why, and how to try again. The use
case ends.

3a. The saver does not agree: no search is made and nothing is shared. The use case ends.

5a. A provider can only say it may hold a pension for the saver, not that it does: it is listed as a possible match,
not a pot, for the saver to claim when they choose
([claim-a-possible-match](../claim-a-possible-match/USE-CASE.md)). The search carries on.

5b. A provider has found the pension but cannot give a value yet: it is added as a pot with no value, saying when one
is expected.

5c. A pension found is one the saver already added: it is not added twice, and its pot is marked as found by the
search too.

6a. No pension is found: the saver is told so, and offered adding an investment portfolio instead
([add-an-investment-portfolio](../add-an-investment-portfolio/USE-CASE.md)).

6b. The saver has left Pot Tracker while the search runs: answers keep arriving, and they are told on their next sign-in
how many pensions were found since they were last there.

## 7 Open Questions (not resolved by this use case)

* Whether the saver can remove a pot found by the search, or only hide it.
* Whether the State Pension is shown, which the service can find too.

## 8 Gate

The end-to-end test a UI slice delivering this use case must pass. Its walkthrough, once drawn, is
`walkthroughs/find-my-pensions`.

* **Main scenario:** ask to find pensions; be told what will happen; prove who you are; agree; see the search start;
  see pensions added as providers answer; be told when it has finished and how many were found.
* **1a:** search again within the year; go straight to the search starting.
* **2a:** fail to prove who you are; be told the search cannot start, why, and how to try again.
* **3a:** decline; see no search started.
* **5a:** receive a possible match; see it listed as one, not as a pot; claim it, as
  [claim-a-possible-match](../claim-a-possible-match/USE-CASE.md)'s gate does.
* **5b:** receive a pension with no value; see it as a pot with no value and when one is expected.
* **5c:** add a pension by hand, then have the search find it; see one pot, not two.
* **6a:** search with no pensions to find; be told so, and offered adding a portfolio.
* **6b:** sign out during a search; sign in after providers have answered; be told how many were found.
