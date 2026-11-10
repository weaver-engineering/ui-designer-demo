# Sign Out

**Actor:** a saver: any of the [mid-career saver](../../user-personas/mid-career-saver.md), the
[near-retirement planner](../../user-personas/near-retirement-planner.md) or the
[hands-on investor](../../user-personas/hands-on-investor.md)
**Scope:** does not cover signing in again ([sign-in](../sign-in/USE-CASE.md)).

## Context
* [Pot Tracker](../../../../PRODUCT.md) - what the product is

## 1 Goal

The saver stops using Pot Tracker on a device, so no one else can see their money there.

## 2 Trigger

The saver has finished, or is leaving a device someone else may use.

## 3 Preconditions

* The saver is signed in on the device ([sign-in](../sign-in/USE-CASE.md)).

## 4 Main Success Scenario

1. The saver asks to sign out.
2. The saver is signed out on that device, and sees the sign-in, with nothing of their pots left on the screen.

## 5 Postconditions

* Nothing the saver set up is lost: their pots, consents, projections' assumptions and transfers under way are kept,
  and are there when they next sign in.
* A transfer or a pension search under way carries on.
* The saver is still signed in on their other devices.

## 6 Extensions

1a. The saver has been away for 15 minutes: they are signed out without asking, and on returning see the sign-in, told
why. Go to 2.

1b. The saver is part way through starting a transfer ([transfer-between-pots](../transfer-between-pots/USE-CASE.md)):
they are asked to confirm, since it has not been sent. On confirming, it is dropped. Go to 2.

## 7 Open Questions (not resolved by this use case)

* Whether to offer signing out of every device at once.

## 8 Gate

The end-to-end test a UI slice delivering this use case must pass. Its walkthrough, once drawn, is
`walkthroughs/sign-out`.

* **Main scenario:** from the overview, ask to sign out; see the sign-in, and nothing of your pots; sign in again and find
  every pot as it was.
* **1a:** leave a signed-in device for 15 minutes; see the sign-in, told you were signed out for being away.
* **1b:** part way through a transfer, ask to sign out; be asked to confirm, and confirm; sign in again and find no
  transfer started.
