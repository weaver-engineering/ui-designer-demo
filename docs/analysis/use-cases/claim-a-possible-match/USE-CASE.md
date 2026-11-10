# Claim A Possible Match

**Actor:** a saver, most often the [mid-career saver](../../user-personas/mid-career-saver.md); any of them may
**Scope:** does not cover how a possible match arises ([find-my-pensions](../find-my-pensions/USE-CASE.md) 5a), or
what the pension is worth once claimed ([see-what-a-pension-is-worth](../see-what-a-pension-is-worth/USE-CASE.md)).

## Context
* [Pot Tracker](../../../../PRODUCT.md) - what the product is
* [Finding Pensions](../../domain/finding-pensions.md) - why a provider can only say it *may* hold a pension, and what
  it asks for to be sure

## 1 Goal

The provider is satisfied that a pension it may hold is the saver's, and shares it, so it becomes one of their pots.

## 2 Trigger

A provider has answered the saver's search with a possible match
([find-my-pensions](../find-my-pensions/USE-CASE.md) 5a): it holds a pension for someone who could be the saver, but
what the search gave it is not enough to be sure.

## 3 Preconditions

* The saver is signed in ([sign-in](../sign-in/USE-CASE.md)).
* The saver has a possible match waiting for them to claim it.

## 4 Main Success Scenario

1. The saver chooses a possible match, and sees what the provider has told them: its name, and why it is not sure.
2. The saver chooses to claim it, and is asked for what the provider needs to be sure. The provider decides what that
   is: the employer they worked for and when, an address they lived at then, a membership number if they have one.
3. The saver gives what they know, and sends it to the provider.
4. The saver is told the provider is checking, and how long it says it will take.
5. The provider confirms the pension is the saver's, and shares it: the saver is told so, and it is one of their pots,
   with its value.

## 5 Postconditions

* The pension is one of the saver's pots, marked as found by the search, and the possible match is gone.
* What the saver gave the provider was sent only to that provider, and Pot Tracker does not keep it.

## 6 Extensions

1a. The saver knows it is not theirs: they say so, and the possible match is dropped. The provider is told. The use case
ends.

2a. The saver does not have what the provider asks for now: they leave it, and the possible match waits for them. The
use case ends.

3a. The saver does not know something the provider asks for, such as a membership number: they say they don't know, and
send what they do.

5a. The provider needs more: it asks a further question, such as to confirm a date of leaving. The saver is told, and
answers. Go to 4.

5b. The provider cannot match it to the saver from what they gave: they are told so, and why if the provider says.
They may try again with different details, or leave it. Go to 2, or the use case ends.

5c. The provider does not answer in the time it said: the saver is told it is late, and may remind it, or leave it to
answer.

## 7 Open Questions (not resolved by this use case)

* How many times the saver may try again before the provider asks them to contact it directly.

## 8 Gate

The end-to-end test a UI slice delivering this use case must pass. Its walkthrough, once drawn, is
`walkthroughs/claim-a-possible-match`. It is drawn nested in
[find-my-pensions](../find-my-pensions/USE-CASE.md) 5a.

* **Main scenario:** choose a possible match; see why the provider isn't sure; claim it; give the employer, dates and
  address asked for; send them; be told it is being checked and for how long; be told it is confirmed, and see it as a
  pot with its value.
* **1a:** say it is not yours; see it gone.
* **2a:** leave it; see it still waiting on your next sign-in.
* **3a:** say you don't know the membership number; send the rest.
* **5a:** be asked a further question; answer it; be told it is being checked again.
* **5b:** be told it could not be matched; try again with a different address.
* **5c:** wait past the time the provider gave; be told it is late; remind it.
