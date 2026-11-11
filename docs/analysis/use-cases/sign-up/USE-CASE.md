# Sign Up

**Actor:** a saver: any of the [mid-career saver](../../user-personas/mid-career-saver.md), the
[near-retirement planner](../../user-personas/near-retirement-planner.md) or the
[hands-on investor](../../user-personas/hands-on-investor.md)
**Scope:** does not cover signing in once signed up ([sign-in](../sign-in/USE-CASE.md)), or proving who they are to
search for their pensions ([find-my-pensions](../find-my-pensions/USE-CASE.md) 2).

## Context
* [Pot Tracker](../../../../PRODUCT.md) - what the product is

## 1 Goal

The saver becomes one of Pot Tracker's users, and can start bringing their pots together.

## 2 Trigger

The saver wants to see their pensions and investments in one place, and is not one of Pot Tracker's users
([sign-in](../sign-in/USE-CASE.md) 2b).

## 3 Preconditions

* None.

## 4 Main Success Scenario

1. The saver asks to sign up.
2. The saver gives their name, and the email address and password they will be known by.
3. The saver agrees to Pot Tracker's terms.
4. The saver confirms that the email address is theirs.
5. The saver is one of Pot Tracker's users, and is signed in ([sign-in](../sign-in/USE-CASE.md) 3). With no pots yet,
   they are offered the two ways to start: finding their pensions
   ([find-my-pensions](../find-my-pensions/USE-CASE.md)) and adding an investment portfolio
   ([add-an-investment-portfolio](../add-an-investment-portfolio/USE-CASE.md)).

## 5 Postconditions

* The saver is one of Pot Tracker's users, with no pots.
* The saver is signed in on the device they signed up on.

## 6 Extensions

2a. The saver chooses to be known by their Google account: they identify themselves to Google, and Pot Tracker takes the
name and email address Google gives. Go to 3.

2b. The email address is already one of Pot Tracker's users: the saver is told so, and offered sign-in instead. Go to 1,
or to [sign-in](../sign-in/USE-CASE.md).

2c. The password is not acceptable: the saver is told why, with what they typed kept but the password. Go to 2.

3a. The saver does not agree to the terms: they are not signed up, and nothing they gave is kept.

4a. The confirmation has expired: the saver is told so, and asks for another. Go to 4.

## 7 Open Questions (not resolved by this use case)

* Whether an address signed up with a password and the same address signed in with Google are one user.

## 8 Gate

The end-to-end test a UI slice delivering this use case must pass. Its walkthrough, once drawn, is
`walkthroughs/sign-up`.

* **Main scenario:** ask to sign up; give a name, email address and password; agree to the terms; confirm the address
  with the code sent to it; be signed in, and be offered finding pensions and adding a portfolio.
* **2a:** choose Google, identify to Google; agree to the terms; be signed in with the name and address Google gives.
* **2b:** give an address already signed up; be told so, and offered sign-in.
* **2c:** give a password Pot Tracker refuses; be told why, with the name and address kept; give another.
* **3a:** decline the terms; be left not signed up, and find the address can sign up again from the start.
* **4a:** confirm with an expired code; be told so; ask for another and confirm with it.
