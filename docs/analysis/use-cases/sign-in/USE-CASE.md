# Sign In

**Actor:** a saver: any of the [mid-career saver](../../user-personas/mid-career-saver.md), the
[near-retirement planner](../../user-personas/near-retirement-planner.md) or the
[hands-on investor](../../user-personas/hands-on-investor.md)
**Scope:** does not cover becoming one of Pot Tracker's users ([sign-up](../sign-up/USE-CASE.md)), or leaving
([sign-out](../sign-out/USE-CASE.md)).

## Context
* [Pot Tracker](../../../../PRODUCT.md) - what the product is

## 1 Goal

The saver is identified to Pot Tracker, and sees where their pots stand.

## 2 Trigger

The saver wants to check on their pensions and investments.

## 3 Preconditions

* The saver is not signed in on the device.
* The saver is one of Pot Tracker's users ([sign-up](../sign-up/USE-CASE.md)).

## 4 Main Success Scenario

1. The saver goes to Pot Tracker.
2. The saver is asked to identify themselves, and does so with their email address and password.
3. The saver is signed in, and sees an overview of their pots: each one's value, and what they add up to.

## 5 Postconditions

* The saver is signed in on the device, and stays so until they sign out or have been away for 15 minutes.
* Nothing about the saver's pots was shown before they were signed in.

## 6 Extensions

2a. The saver chooses to identify themselves with their Google account: they identify themselves to Google. Go to 3.

2b. The saver cannot be identified, whether the password is wrong, or they, or their Google account, are not one of
Pot Tracker's users: they are told so, without being told which, and offered sign-up. Go to 2, or to
[sign-up](../sign-up/USE-CASE.md).

2c. The saver has forgotten their password: they ask to reset it, and are sent a link to the email address they gave;
following it, they choose a new password. Go to 2.

3a. The saver has no pots yet: they are offered the two ways to start, as on signing up
([sign-up](../sign-up/USE-CASE.md) 5).

3b. Some pots' values could not be brought up to date: each is shown with the value last known and when that was.

## 7 Open Questions (not resolved by this use case)

* Whether a second factor is asked for, as banking apps do. Not for the sample.

## 8 Gate

The end-to-end test a UI slice delivering this use case must pass. Its walkthrough, once drawn, is
`walkthroughs/sign-in`.

* **Main scenario:** go to Pot Tracker signed out and see the sign-in, and nothing of anyone's pots; identify with an
  email address and password; see the overview of your pots and their total.
* **2a:** choose Google, identify to Google; see the overview.
* **3a:** identify with a wrong password, and with an address that is not a user; be told so without being told which,
  with the address kept and the password not.
* **3b:** ask to reset the password; follow the link sent; choose a new one; sign in with it.
* **3c:** sign in with no pots; be offered finding pensions and adding a portfolio.
* **3d:** sign in while one provider cannot be reached; see that pot's last known value, and when it was.
