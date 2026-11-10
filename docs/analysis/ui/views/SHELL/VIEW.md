# SHELL

<!-- ui-walkthrough: view begin. Generated from VIEW.yaml and VIEW.html; edit those, not this block. -->
The frame around everything a signed-in saver does: Pot Tracker's name, where they can go, who they are and signing out, and what they are doing in the middle. On a phone, where they can go moves to a bar at the bottom.

![SHELL as drawn, its slots showing their placeholders](VIEW.png)

**Slots**

| Slot | Holds | How many | Description |
|---|---|---|---|
| `MAIN` | [OVERVIEW](../OVERVIEW/VIEW.md), [FIND-PENSIONS](../FIND-PENSIONS/VIEW.md), [CLAIM](../CLAIM/VIEW.md) | one | What the saver is doing. |

**Components**

| Component | Bindings | Description |
|---|---|---|
| `NAV-OVERVIEW` |  | Goes to the overview of every pot. |
| `NAV-GROWTH` |  | Goes to comparing growth. |
| `NAV-TRANSFERS` |  | Goes to the saver's transfers. |
| `SAVER` | text: `saver` | Who is signed in. |
| `SIGN-OUT` |  | Signs the saver out of this device. |
<!-- ui-walkthrough: view end -->

<!-- ui-walkthrough: begin. Generated from VIEW.html and VIEW.yaml; edit those, not this block. -->
**Used by**

* Claim a possible match: 01 Choose a possible match ([desk](../../walkthroughs/claim-a-possible-match/01-choose/STEP.desk.md) · [phone](../../walkthroughs/claim-a-possible-match/01-choose/STEP.phone.md))
* Claim a possible match: 01a Say it is not theirs ([desk](../../walkthroughs/claim-a-possible-match/01a-not-mine/STEP.desk.md) · [phone](../../walkthroughs/claim-a-possible-match/01a-not-mine/STEP.phone.md))
* Claim a possible match: 02 Be asked what the provider needs ([desk](../../walkthroughs/claim-a-possible-match/02-claim/STEP.desk.md) · [phone](../../walkthroughs/claim-a-possible-match/02-claim/STEP.phone.md))
* Claim a possible match: 02a Leave it for now ([desk](../../walkthroughs/claim-a-possible-match/02a-leave/STEP.desk.md) · [phone](../../walkthroughs/claim-a-possible-match/02a-leave/STEP.phone.md))
* Claim a possible match: 03 Give what they know ([desk](../../walkthroughs/claim-a-possible-match/03-give/STEP.desk.md) · [phone](../../walkthroughs/claim-a-possible-match/03-give/STEP.phone.md))
* Claim a possible match: 03a Not know the membership number ([desk](../../walkthroughs/claim-a-possible-match/03a-dont-know/STEP.desk.md) · [phone](../../walkthroughs/claim-a-possible-match/03a-dont-know/STEP.phone.md))
* Claim a possible match: 04 Be told the provider is checking ([desk](../../walkthroughs/claim-a-possible-match/04-checking/STEP.desk.md) · [phone](../../walkthroughs/claim-a-possible-match/04-checking/STEP.phone.md))
* Claim a possible match: 05 See it confirmed as theirs ([desk](../../walkthroughs/claim-a-possible-match/05-confirmed/STEP.desk.md) · [phone](../../walkthroughs/claim-a-possible-match/05-confirmed/STEP.phone.md))
* Claim a possible match: 05a Answer a further question ([desk](../../walkthroughs/claim-a-possible-match/05a-further-question/STEP.desk.md) · [phone](../../walkthroughs/claim-a-possible-match/05a-further-question/STEP.phone.md))
* Claim a possible match: 05b Be told it could not be matched ([desk](../../walkthroughs/claim-a-possible-match/05b-not-matched/STEP.desk.md) · [phone](../../walkthroughs/claim-a-possible-match/05b-not-matched/STEP.phone.md))
* Claim a possible match: 05c Be told the provider is late ([desk](../../walkthroughs/claim-a-possible-match/05c-late/STEP.desk.md) · [phone](../../walkthroughs/claim-a-possible-match/05c-late/STEP.phone.md))
* Find my pensions: 01 Ask to find their pensions ([desk](../../walkthroughs/find-my-pensions/01-ask/STEP.desk.md) · [phone](../../walkthroughs/find-my-pensions/01-ask/STEP.phone.md))
* Find my pensions: 01a Search again within the year ([desk](../../walkthroughs/find-my-pensions/01a-searched-before/STEP.desk.md) · [phone](../../walkthroughs/find-my-pensions/01a-searched-before/STEP.phone.md))
* Find my pensions: 02 Prove who they are ([desk](../../walkthroughs/find-my-pensions/02-prove/STEP.desk.md) · [phone](../../walkthroughs/find-my-pensions/02-prove/STEP.phone.md))
* Find my pensions: 02a Cannot prove who they are ([desk](../../walkthroughs/find-my-pensions/02a-not-proved/STEP.desk.md) · [phone](../../walkthroughs/find-my-pensions/02a-not-proved/STEP.phone.md))
* Find my pensions: 03 Agree to the search ([desk](../../walkthroughs/find-my-pensions/03-agree/STEP.desk.md) · [phone](../../walkthroughs/find-my-pensions/03-agree/STEP.phone.md))
* Find my pensions: 03a Decline the search ([desk](../../walkthroughs/find-my-pensions/03a-declined/STEP.desk.md) · [phone](../../walkthroughs/find-my-pensions/03a-declined/STEP.phone.md))
* Find my pensions: 04 See the search start ([desk](../../walkthroughs/find-my-pensions/04-started/STEP.desk.md) · [phone](../../walkthroughs/find-my-pensions/04-started/STEP.phone.md))
* Find my pensions: 05 See pensions arrive ([desk](../../walkthroughs/find-my-pensions/05-pensions-arrive/STEP.desk.md) · [phone](../../walkthroughs/find-my-pensions/05-pensions-arrive/STEP.phone.md))
* Find my pensions: 05a Receive a possible match ([desk](../../walkthroughs/find-my-pensions/05a-possible-match/STEP.desk.md) · [phone](../../walkthroughs/find-my-pensions/05a-possible-match/STEP.phone.md))
* Find my pensions: 05b Receive a pension with no value yet ([desk](../../walkthroughs/find-my-pensions/05b-no-value-yet/STEP.desk.md) · [phone](../../walkthroughs/find-my-pensions/05b-no-value-yet/STEP.phone.md))
* Find my pensions: 05c Find a pension already added ([desk](../../walkthroughs/find-my-pensions/05c-already-added/STEP.desk.md) · [phone](../../walkthroughs/find-my-pensions/05c-already-added/STEP.phone.md))
* Find my pensions: 06 Be told the search has finished ([desk](../../walkthroughs/find-my-pensions/06-finished/STEP.desk.md) · [phone](../../walkthroughs/find-my-pensions/06-finished/STEP.phone.md))
* Find my pensions: 06a Find no pensions ([desk](../../walkthroughs/find-my-pensions/06a-none-found/STEP.desk.md) · [phone](../../walkthroughs/find-my-pensions/06a-none-found/STEP.phone.md))
* Find my pensions: 06b Be told what was found while away ([desk](../../walkthroughs/find-my-pensions/06b-told-on-sign-in/STEP.desk.md) · [phone](../../walkthroughs/find-my-pensions/06b-told-on-sign-in/STEP.phone.md))
* Sign in: 03 See where their pots stand ([desk](../../walkthroughs/sign-in/03-overview/STEP.desk.md) · [phone](../../walkthroughs/sign-in/03-overview/STEP.phone.md))
* Sign in: 03a Start with no pots ([desk](../../walkthroughs/sign-in/03a-no-pots/STEP.desk.md) · [phone](../../walkthroughs/sign-in/03a-no-pots/STEP.phone.md))
* Sign in: 03b See a value that is not up to date ([desk](../../walkthroughs/sign-in/03b-not-up-to-date/STEP.desk.md) · [phone](../../walkthroughs/sign-in/03b-not-up-to-date/STEP.phone.md))
<!-- ui-walkthrough: end -->
