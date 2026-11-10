# Pots, Providers And Money Moved

The things Pot Tracker tracks: the saver's pots, who holds them, and the money that moves into, out of and between them.

## Context
* [Pot Tracker](../../../PRODUCT.md) - the root index for this repo
* [Finding Pensions](finding-pensions.md) - how pensions arrive as pots
* [Normalising Growth](normalising-growth.md) - why money moved is recorded apart from growth

## 1 Pots

**A pot is one pension or investment account the saver holds.** Each has a provider, a kind, a name the saver knows it
by, a value and the date of that value, and how it came to Pot Tracker.

| Kind | What it is |
|---|---|
| **Workplace pension** | A pot of money an employer paid into, and the saver too. Most savers have several, one for each job. |
| **Personal pension** | A pot of money the saver set up themselves, including a self-invested personal pension (SIPP), where they choose the investments. |
| **Promised-income pension** | A workplace pension that promises a yearly income from the scheme's retirement age, set by salary and years worked, rather than a pot of money (defined benefit). |
| **Stocks and shares ISA** | An investment account whose growth is free of tax, paid into up to £20,000 a year. |
| **General investment account** | An investment account with no tax wrapper and no limit. |

The first three are pensions. **A pot holds investments**, except a promised-income pension, which holds a promise.
A pot of investments has holdings: each fund or share, how many units, and their value.

## 2 How A Pot Comes To Pot Tracker

| How | Kept up to date | Holdings | History |
|---|---|---|---|
| **Found by the search** ([Finding Pensions](finding-pensions.md)) | Monthly, while consent lasts | No | From when found |
| **Connected** to a platform ([add-an-investment-portfolio](../use-cases/add-an-investment-portfolio/USE-CASE.md)) | Each day, while consent lasts (90 days, renewable) | Yes | As far back as the platform gives |
| **Added by hand** | Only when the saver updates it | If the saver gives them | Only what the saver gives |

A pot can be both found and connected: the same pension, found by the search and connected through its platform, is one
pot.

## 3 Providers

**A provider is who holds a pot**: a pension scheme, an insurer or an investment platform. The saver deals with each
separately in the world; Pot Tracker shows them together. A provider is shown by its name, never by a scheme reference.

## 4 Money Moved

Every movement of money into, out of or between pots is recorded, apart from the pot's value, so it is never mistaken
for growth ([Normalising Growth](normalising-growth.md)).

| Movement | From | To |
|---|---|---|
| **Payment in** | Outside: the saver's bank, their employer | A pot |
| **Withdrawal** | A pot | Outside: the saver's bank |
| **Transfer** | One of the saver's pots | Another of them |

Payments in by an employer arrive from the provider; they are not started in Pot Tracker. Every other movement may be
([transfer-between-pots](../use-cases/transfer-between-pots/USE-CASE.md)).

## 5 What May Move Where

| From \ To | Pension | ISA | General account | Bank |
|---|---|---|---|---|
| **Pension** | Yes, whole; part where the provider allows | No | No | Only from 57 |
| **Promised-income pension** | Yes, whole; regulated advice first if worth over £30,000 | No | No | Only from the scheme's age, as income |
| **ISA** | No: pay in from the bank instead | Yes, whole or part, keeping it an ISA | Yes, as a withdrawal and payment in | Yes |
| **General account** | No: pay in from the bank instead | Yes, within the year's £20,000 | Yes | Yes |
| **Bank** | Yes, as a payment in | Yes, within the year's £20,000 | Yes | — |

A pot added by hand cannot be moved from or to, since Pot Tracker has no connection to its provider.

## 6 A Transfer's Stages

```
asked for ──▶ agreed ──▶ money moving ──▶ done
    │            │
    └──▶ cancelled (by the saver, before money moves)
    └────────────┴──▶ refused (by either provider)
```

| Stage | Means | Typically |
|---|---|---|
| **Asked for** | Sent to the provider the money goes to, which asks the one it comes from. | A day or two |
| **Agreed** | The provider it comes from has agreed, and is selling the investments. | Up to two weeks for a pension |
| **Money moving** | Sold, and the money is on its way. Out of the market until it arrives. | A few days |
| **Done** | Arrived, and invested at the receiving pot. | |

Each stage's date is kept. A stage that runs past its typical time is late, and the saver is told which provider it
waits on.
