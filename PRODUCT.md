# Pot Tracker

## Context
* [README](README.md) - what this repository is, and how to start designing its UI
* [Glossary](docs/glossary.md) - one-line definitions of every term used here
* [UI Principles](docs/analysis/ui/PRINCIPLES.md) - what the UI must be, its viewports, and its look
* **Who it is for:** the [mid-career saver](docs/analysis/user-personas/mid-career-saver.md), the
  [near-retirement planner](docs/analysis/user-personas/near-retirement-planner.md) and the
  [hands-on investor](docs/analysis/user-personas/hands-on-investor.md)
* **What it does:** the use cases in [docs/analysis/use-cases](docs/analysis/use-cases)
* **What it knows:** the analysis in [docs/analysis/domain](docs/analysis/domain)

## 1 What It Is

Pot Tracker shows a saver every pension and investment pot they have, in one place, and how each is doing.

Most people in the UK have a pension from every job they have had, and lose track of some. They may have an ISA or a
self-invested pension with a platform as well. Each provider has its own website, its own sign-in and its own way of
showing a value, and none of them shows the others. Pot Tracker brings them together:

* **It finds their pensions**, through an outside pension-finding service, including the ones they had forgotten.
* **It adds their investment accounts**, connected to the platform, or by hand.
* **It says what a pension is worth now, and what it might be worth at retirement**, every pension on the same
  assumptions, so the projections add up.
* **It moves money**: transfers between pots, and payments in and out, followed until they are done.
* **It compares growth on the same terms**: each pot's growth with the money moved in and out taken out of it, so
  saving more never looks like investing well.

## 2 What It Is Not

* **Not advice.** Pot Tracker shows; it never recommends a pot, a fund or a transfer. A projection is an illustration.
* **Not a provider.** It holds no money. Every transfer is carried out by the providers involved.
* **Not real.** Pot Tracker is a sample product, made to try the UI Designer on. Its analysis is plausible, and its
  rules follow the UK's in outline, but no part of it has been checked as the law or a regulator would.

## 3 What Is Here, And What Is Not

This repository holds Pot Tracker's **analysis**: who it is for, what they do with it, what it needs to know, and how it
should look. It does not hold its UI design: that is what you make, with the `ui-walkthrough` skill, in your fork
([README](README.md)).
