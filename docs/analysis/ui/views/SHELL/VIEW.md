# SHELL

<!-- ui-walkthrough: view begin. Generated from VIEW.yaml and VIEW.html; edit those, not this block. -->
The frame around everything a signed-in saver does: Pot Tracker's name, where they can go, who they are and signing out, and what they are doing in the middle. On a phone, where they can go moves to a bar at the bottom.

![SHELL as drawn, its slots showing their placeholders](VIEW.png)

**Slots**

| Slot | Holds | How many | Description |
|---|---|---|---|
| `MAIN` | [OVERVIEW](../OVERVIEW/VIEW.md), [FIND-PENSIONS](../FIND-PENSIONS/VIEW.md) | one | What the saver is doing. |

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
