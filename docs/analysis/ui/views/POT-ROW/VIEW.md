# POT-ROW

<!-- ui-walkthrough: view begin. Generated from VIEW.yaml and VIEW.html; edit those, not this block. -->
One pot in a list: its colour, its name, its provider and kind, and its value with when that was.

![POT-ROW as drawn, its slots showing their placeholders](VIEW.png)

**Components**

| Component | Bindings | Description |
|---|---|---|
| `NAME` | text: `pot.name` | The name the saver knows the pot by. |
| `PROVIDER` | text: `pot.provider` | Who holds the pot. |
| `KIND` | text: `pot.kind` | What kind of pot it is, in plain words. |
| `VALUE` | text: `pot.value` | Its value, in pounds. |
| `AS-OF` | text: `pot.as-of` | When the value was brought up to date. |
| `AWAITING` | visible: `awaiting` | Says the value is still to come, in place of a value. |
| `EXPECTED` | visible: `awaiting` | Says the date is when a value is expected. |
| `FOUND` | visible: `found != no` | Marks a pot the pension search found. |
| `MATCHED` | visible: `found == matched` | Says the search found a pot the saver had already added, so it was not added twice. |
| `LAST-KNOWN` | visible: `stale` | Says the value is the last known, because it could not be brought up to date. |
<!-- ui-walkthrough: view end -->

<!-- ui-walkthrough: begin. Generated from VIEW.html and VIEW.yaml; edit those, not this block. -->
**Used by**

* Find my pensions: 01 Ask to find their pensions ([desk](../../walkthroughs/find-my-pensions/01-ask/STEP.desk.md) · [phone](../../walkthroughs/find-my-pensions/01-ask/STEP.phone.md))
* Find my pensions: 05 See pensions arrive ([desk](../../walkthroughs/find-my-pensions/05-pensions-arrive/STEP.desk.md) · [phone](../../walkthroughs/find-my-pensions/05-pensions-arrive/STEP.phone.md))
* Find my pensions: 05a Receive a possible match ([desk](../../walkthroughs/find-my-pensions/05a-possible-match/STEP.desk.md) · [phone](../../walkthroughs/find-my-pensions/05a-possible-match/STEP.phone.md))
* Find my pensions: 05b Receive a pension with no value yet ([desk](../../walkthroughs/find-my-pensions/05b-no-value-yet/STEP.desk.md) · [phone](../../walkthroughs/find-my-pensions/05b-no-value-yet/STEP.phone.md))
* Find my pensions: 05c Find a pension already added ([desk](../../walkthroughs/find-my-pensions/05c-already-added/STEP.desk.md) · [phone](../../walkthroughs/find-my-pensions/05c-already-added/STEP.phone.md))
* Find my pensions: 06 Be told the search has finished ([desk](../../walkthroughs/find-my-pensions/06-finished/STEP.desk.md) · [phone](../../walkthroughs/find-my-pensions/06-finished/STEP.phone.md))
* Find my pensions: 06b Be told what was found while away ([desk](../../walkthroughs/find-my-pensions/06b-told-on-sign-in/STEP.desk.md) · [phone](../../walkthroughs/find-my-pensions/06b-told-on-sign-in/STEP.phone.md))
* Sign in: 03 See where their pots stand ([desk](../../walkthroughs/sign-in/03-overview/STEP.desk.md) · [phone](../../walkthroughs/sign-in/03-overview/STEP.phone.md))
* Sign in: 03b See a value that is not up to date ([desk](../../walkthroughs/sign-in/03b-not-up-to-date/STEP.desk.md) · [phone](../../walkthroughs/sign-in/03b-not-up-to-date/STEP.phone.md))
<!-- ui-walkthrough: end -->
