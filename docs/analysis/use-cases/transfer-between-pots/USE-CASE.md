# Transfer Between Pots

**Actor:** a saver, most often the [near-retirement planner](../../user-personas/near-retirement-planner.md) or the
[hands-on investor](../../user-personas/hands-on-investor.md); any of them may
**Scope:** does not cover what a transfer does to a pot's growth ([compare-growth](../compare-growth/USE-CASE.md)), or
advice on whether to transfer, which Pot Tracker does not give.

## Context
* [Pot Tracker](../../../../PRODUCT.md) - what the product is
* [Pots, Providers and Money Moved](../../domain/pots-and-providers.md) - which moves are allowed between which kinds of
  pot, and the stages a transfer goes through

## 1 Goal

The saver moves money from one pot to another, or into or out of a pot, and can see where it has got to until it is
done.

## 2 Trigger

The saver wants to bring pots together, move money to where it does better, or pay in or take out.

## 3 Preconditions

* The saver is signed in ([sign-in](../sign-in/USE-CASE.md)).
* The saver has at least one pot connected to its provider: a pot added by hand cannot be moved from or to.

## 4 Main Success Scenario

1. The saver asks to see their transfers, and sees those under way, each with the stage it has reached, and those done.
2. The saver asks to start a transfer, and chooses the pot it is from and the pot it is to.
3. The saver chooses how much: the whole pot or, where the pot allows, a part.
4. The saver is shown what the transfer means before it is sent: any charge for leaving, how long it is expected to
   take, and that the money will be out of the market while it moves.
5. The saver confirms, and the transfer is sent to the provider it is to.
6. As the transfer moves on, the saver sees it reach each stage: asked for, agreed by the provider it is from, money
   moving, done.
7. When it is done, the saver is told, and sees both pots' values as they now are.

## 5 Postconditions

* The transfer is in the saver's transfers, with the date of each stage, and the amount that arrived.
* Each pot's history records the money that left or arrived, so it is not mistaken for growth
  ([compare-growth](../compare-growth/USE-CASE.md)).

## 6 Extensions

2a. The saver pays into a pot from their bank account, or takes money out of a pot to it: they choose the pot and the
bank account in place of the other pot. Go to 3.

2b. The move is not allowed between those kinds of pot, such as from a pension into an ISA, or out of a pension before
the age it can be taken: the saver is told why, and what they could do instead. Go to 2.

4a. The pot it is from is a promised-income pension worth more than £30,000 if transferred: the saver is told the law
requires them to take regulated advice first, and asked to confirm they have. If they have not, the transfer is not
sent. The use case ends.

5a. The saver changes their mind before confirming: nothing is sent. The use case ends.

6a. The saver cancels a transfer before the money moves: the provider is asked to stop it, and the saver sees it
cancelled once it has. After the money moves it cannot be cancelled.

6b. A provider refuses the transfer: the saver is told which, and why if it says. The transfer ends, refused, and no
money has moved.

6c. A stage takes longer than expected: the saver is told it is late, and which provider it is waiting on.

## 7 Open Questions (not resolved by this use case)

* Whether a transfer can be chosen between pots at the same provider, which providers do themselves.
* Whether the saver is told of a transfer started elsewhere, at a provider, when its money arrives.

## 8 Gate

The end-to-end test a UI slice delivering this use case must pass. Its walkthrough, once drawn, is
`walkthroughs/transfer-between-pots`.

* **Main scenario:** see transfers under way and done; start one; choose from and to; choose the whole pot; see the
  charge, time and time out of the market; confirm; see it reach each stage; be told it is done, and see both pots'
  new values.
* **2a:** pay into an ISA from a bank account; see it reach each stage.
* **2b:** choose a pension into an ISA; be told it is not allowed and why.
* **4a:** choose a promised-income pension worth £45,000; be told advice is required; say you have not taken it; see
  nothing sent.
* **5a:** reach the confirmation and go back; see nothing sent.
* **6a:** cancel a transfer while it waits for the provider to agree; see it cancelled.
* **6b:** have the provider refuse; be told so and why.
* **6c:** have a stage run late; be told so, and who it waits on.
