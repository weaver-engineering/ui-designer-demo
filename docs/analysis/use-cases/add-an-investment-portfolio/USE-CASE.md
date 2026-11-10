# Add An Investment Portfolio

**Actor:** a saver, most often the [hands-on investor](../../user-personas/hands-on-investor.md); any of them may
**Scope:** does not cover workplace and personal pensions the pension-finding service finds
([find-my-pensions](../find-my-pensions/USE-CASE.md)), or comparing how a portfolio has grown
([compare-growth](../compare-growth/USE-CASE.md)).

## Context
* [Pot Tracker](../../../../PRODUCT.md) - what the product is
* [Pots, Providers and Money Moved](../../domain/pots-and-providers.md) - the kinds of pot, and what a holding is

## 1 Goal

An investment account the saver holds with a platform, such as an ISA, a general investment account or a
self-invested pension, is one of their pots in Pot Tracker, with its holdings and value kept up to date.

## 2 Trigger

The saver holds an investment account the pension-finding service will not find, and wants it alongside their
pensions.

## 3 Preconditions

* The saver is signed in ([sign-in](../sign-in/USE-CASE.md)).

## 4 Main Success Scenario

1. The saver asks to add an investment portfolio.
2. The saver chooses their platform from those Pot Tracker can connect to.
3. The saver signs in to the platform, at the platform, and agrees to share their accounts with Pot Tracker.
4. The saver is shown the accounts the platform shares, each with its kind, its value and its holdings, and chooses
   the ones to add.
5. The saver gives each a name they will know it by, or keeps the platform's.
6. Each account chosen is one of the saver's pots, with its holdings, its value, and the money paid in and taken out of
   it since it was opened.

## 5 Postconditions

* Each account added is a pot, connected to its platform and kept up to date each day.
* The saver's consent to the platform sharing is recorded, with when it ends, which is 90 days later unless renewed.

## 6 Extensions

2a. The saver's platform is not one Pot Tracker can connect to: they choose to add the account by hand. They give its
kind, its platform, its name and its value today, and, if they wish, its holdings. Go to 6. A pot added by hand is kept
up to date only by the saver, and has no history of money paid in or taken out until they give it.

3a. The saver cannot sign in to the platform, or does not agree to share: nothing is added, and they are told so. Go
to 2.

4a. An account the platform shares is already one of the saver's pots: it is shown as added, and cannot be chosen
again.

6a. The platform gives no history before a date: the pot's history starts there, and the saver is told so.

## 7 Open Questions (not resolved by this use case)

* What happens to a connected pot when its consent ends and is not renewed: whether it keeps its last value, as a pot
  added by hand.
* Whether a holding's value is shown in its own currency as well as in pounds.

## 8 Gate

The end-to-end test a UI slice delivering this use case must pass. Its walkthrough, once drawn, is
`walkthroughs/add-an-investment-portfolio`.

* **Main scenario:** ask to add a portfolio; choose a platform; sign in there and agree; choose two of the three accounts
  shared; rename one; see both as pots with their holdings, value and history.
* **2a:** choose to add by hand; give the kind, platform, name and value; see it as a pot with that value and no
  history.
* **3a:** decline at the platform; be told nothing was added; be back at choosing a platform.
* **4a:** add a platform's accounts again; see those already added marked so, and not choosable.
* **6a:** add an account whose history the platform gives only from a date; be told so.
