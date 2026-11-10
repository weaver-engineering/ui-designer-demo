# POSSIBLE-MATCH

<!-- ui-walkthrough: view begin. Generated from VIEW.yaml and VIEW.html; edit those, not this block. -->
A pension a provider may hold for the saver but is not sure is theirs: who the provider is, why it is not sure, and claiming it or saying it is not theirs. It is not a pot until the provider is sure.

![POSSIBLE-MATCH as drawn, its slots showing their placeholders](VIEW.png)

**Components**

| Component | Bindings | Description |
|---|---|---|
| `PROVIDER` | text: `match.provider` | The provider that may hold the pension. |
| `REASON` | text: `match.reason` | Why the provider is not sure, in its own words. |
| `RECEIVED` | text: `match.received` | When the provider answered. |
| `CLAIM` |  | Starts claiming the pension: giving the provider what it needs to be sure. |
| `NOT-MINE` |  | Says the pension is not the saver's, so the possible match is dropped. |
<!-- ui-walkthrough: view end -->

<!-- ui-walkthrough: begin. Generated from VIEW.html and VIEW.yaml; edit those, not this block. -->
**Used by**

* Find my pensions: 05a Receive a possible match ([desk](../../walkthroughs/find-my-pensions/05a-possible-match/STEP.desk.md) · [phone](../../walkthroughs/find-my-pensions/05a-possible-match/STEP.phone.md))
<!-- ui-walkthrough: end -->
