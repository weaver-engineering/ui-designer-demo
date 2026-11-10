# UI Principles

## Context
* [Pot Tracker](../../../PRODUCT.md) - what the product is
* The savers the UI serves: the [mid-career saver](../user-personas/mid-career-saver.md), the
  [near-retirement planner](../user-personas/near-retirement-planner.md) and the
  [hands-on investor](../user-personas/hands-on-investor.md)
* [Glossary](../../glossary.md) - one-line definitions of every term used here

**The use cases are the specification.** A use case says what the saver is trying to do, step by step; a view says
which of those steps it serves, and how, with one wireframe. **The look is the design tokens' alone**
([tokens.css](tokens.css)): colour, type, spacing and shape. No use case or view names a colour.
[look-and-feel.html](look-and-feel.html) shows the tokens in use.

This page holds what the UI must be, before it is designed. **The view tree**, which views there are and how they nest,
**is the design's to add**, here, as it is drawn.

## 1 Principles

1. **The use cases are the specification.** Every view exists to serve use-case steps, and every step is served by a
   view. A step says what the saver does, never how: a view decides how.
2. **Plain words, never references.** A provider by its name, a pot by the name the saver knows it by, money in pounds.
   Never a scheme reference, a policy number where a name exists, or a code.
3. **Every value has its date.** A value is shown with when it was last brought up to date, and one that could not be
   is shown as the value last known, saying when ([sign-in](../use-cases/sign-in/USE-CASE.md) 3d).
4. **A projection is never a promise.** It is shown in today's money, with its assumptions beside it, and as an
   illustration ([Projecting A Retirement Value](../domain/projecting-a-retirement-value.md)).
5. **Nothing of the saver's money is shown to anyone else.** Before signing in, and after signing out, the screen holds
   nothing of their pots.
6. **What takes days is followed, not waited for.** A search, a possible match being checked, a transfer: each says
   where it has got to, and the saver is told when it moves on, there and on their next sign-in. Nothing waits on a
   spinner for longer than a page takes to load.
7. **A pot keeps its colour.** Each pot has a colour of its own, the same on every chart and wherever the pot is shown
   beside others, so a line, a bar and a row are recognised as the same pot.
8. **Everything links.** A pot, a transfer, a possible match and a projection each have an address, so a saver can
   return to it, and anything that names one opens it.
9. **The UI decides nothing Pot Tracker does not.** What the saver does through it, Pot Tracker does: the UI gives no
   advice of its own.

## 2 Viewports

| Viewport | Size | Who, and for what |
|---|---|---|
| **Desk** | 1440 × 900 | The hands-on investor analysing growth; the near-retirement planner working through a projection or a transfer |
| **Tablet** | 1024 × 768 | The near-retirement planner, reading carefully |
| **Phone** | 390 × 844 | The mid-career saver, and every saver checking in: the overview, a search's progress, a transfer's stage |

Each view's wireframe is drawn at desk. Its `VIEW.md` says how it lays out on the others. Every use case is served on
every viewport; a chart on a phone may show fewer pots at once, but never fewer use-case steps.
