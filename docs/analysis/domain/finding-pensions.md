# Finding Pensions

How Pot Tracker finds a saver's pensions, including those they have lost track of, through an outside pension-finding
service, and what that service can and cannot say.

## Context
* [Pot Tracker](../../../PRODUCT.md) - the root index for this repo
* [find-my-pensions](../use-cases/find-my-pensions/USE-CASE.md) and
  [claim-a-possible-match](../use-cases/claim-a-possible-match/USE-CASE.md) - the use cases this serves
* [Pots, Providers and Money Moved](pots-and-providers.md) - what a pension found becomes

## 1 The Pension-Finding Service

**Pot Tracker does not search for pensions itself.** An outside pension-finding service does, on the saver's behalf,
and Pot Tracker receives what it finds. The service is modelled on the UK's pensions dashboards: every pension provider
is connected to it, and searches its own records when asked.

It is an external dependency. Pot Tracker cannot make it faster, and cannot see what a provider holds except through
it.

## 2 Proving Who The Saver Is

Before a search, the saver proves who they are to the service's identity check, never to Pot Tracker. What the check
asks for is the service's to decide: typically their name, date of birth, address and National Insurance number, and a
photo of an identity document. Pot Tracker sees only whether it succeeded.

## 3 Consent

The saver agrees to two things, separately: that the service may search for their pensions, and that Pot Tracker may
receive what it finds. **Consent lasts a year.** While it lasts, a search may be run again without asking, and values
are refreshed (§4). When it ends, nothing new arrives until the saver agrees again; what had arrived is kept.

## 4 What A Provider Answers

Each provider searches its records and answers in its own time. **Answers arrive over days, not seconds**: most within
a day, some taking up to a week. Each answer is one of:

| Answer | What it means | What it becomes |
|---|---|---|
| **Match** | The provider is sure the pension is the saver's. | A pot, with what the provider shares (below). |
| **Possible match** | The provider holds a pension for someone who could be the saver, but is not sure. | A possible match, for the saver to claim ([claim-a-possible-match](../use-cases/claim-a-possible-match/USE-CASE.md)). |
| **Nothing** | The provider holds no pension for the saver. | Nothing shown, but counted when the search finishes. |

A provider sharing a pension gives: its own name, the employer the pension came from, if any, whether it is a pot of
money or a promised income, its value and the date of that value, and the retirement age the scheme assumes. **It does
not give holdings, or a history**: a pension found has a history only from when it was found, built from each value the
service refreshes, monthly while consent lasts. A provider may share a pension before it has a value, giving the date
one is expected.

## 5 Possible Matches

A provider can only say it *may* hold a pension when the details the search gave it partly match its records: an old
address, a name since changed, a date of birth it never held. **To be sure, it asks the saver for more**, and decides
what to ask: the employer they worked for and when, an address they lived at then, a membership number if they have
one. It may ask a further question once it has the answers.

What the saver gives goes to that provider only, through the service. Pot Tracker passes it on and does not keep it.
The provider answers in a time it states, typically up to ten working days, with a match or with no match and, if it
chooses, why.

## 6 What This Means For The UI

* A search is not a wait on a spinner: it starts, and the saver is told as answers arrive, including on a later
  sign-in.
* A pot found by the search is marked so, and has no holdings and a short history.
* A possible match is a thing in its own right, waiting on the saver, not a pot with a flag.
