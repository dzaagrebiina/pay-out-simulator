# Payout & Fee Simulator

**Capstone project - Finance & AI Analyst Internship, [Lunim Intelligence](https://lunim.io), June–September 2026**

A decision-intelligence tool for independent film financing: models the full economics of a deal in one place, before anyone signs. Built to solve a real problem Lunim identified - deals in the independent film industry are often vague, fragile, or unenforceable because neither side can see the numbers clearly until it is too late.

**[→ Open the simulator](https://dzaagrebiina.github.io/pay-out-simulator/)**
No install, no sign-in, no build step. Everything runs in the browser - all libraries are embedded in the file itself.

---

## The problem it solves

Independent film deals involve three separate financial questions that are usually modelled in isolation (or not at all):

1. *How should the production budget be allocated?*
2. *How will investor funds be released as the project progresses?*
3. *If the film makes money, who gets what - and in what order?*

Answering any one of these without the others produces an incomplete picture. This tool connects all three so that creators and investors can stress-test a deal together before committing.

---

## What it does

Three financial engines, fully connected - change any input and all three update instantly.

| Engine | What it models |
|--------|----------------|
| **1  Budget** | Splits the production budget across six research-backed categories (Above the Line, Production, Post-Production, Distribution & Marketing, Development & Rights, Contingency), with a production sub-split and a payroll fringe toggle calibrated for New York / New Jersey union rates |
| **2  Milestone payouts** | Models on-chain escrow: locks the all-in total and releases it in tranches as milestones are met, minus a platform fee and a per-release network (gas) cost; milestones are fully editable - rename, reweight, add or remove |
| **3  Revenue waterfall** | Distributes gross revenue in the correct recoupment order - distribution fee → sales agent fee → P&A recoupment → investor recoupment (with premium) → net profit split - and outputs investor multiple, ROI %, and break-even gross |

The New York / New Jersey tax credit toggle is the headline lever: it reduces equity at risk and visibly lifts investor returns across all three engines in real time.

---

## Key features

- **Typed input + smooth slider** - enter an exact figure or drag; presets for Micro / Low indie / Mid indie / High-end
- **Currency switcher** - USD (default), EUR, GBP
- **Payroll fringe toggle** - 28% default on a 0–40% scale (Non-union → Union scale)
- **Out-of-range amber flag** - marks any percentage outside its researched industry range
- **Normalise button** - one click re-weights all sliders to sum to 100%
- **Custom milestones** - rename, reweight, add or remove; optional holdback carved from the final release
- **P&A link** - P&A recoupment linked to the budget's D&M line by default, or overridable
- **Tax credit toggle** - NY/NJ 30% default, 0–40% range; reduces equity at risk in real time
- **Investor return card** - capital in → tax credit recovered → recoup from revenue → profit share → total back, multiple (×), ROI %, break-even gross

---

## Research basis

All defaults are calibrated for the **US independent film market, with a primary focus on New York and New Jersey**, sourced from industry publications:

| Parameter | Default | Market range | Source |
|-----------|---------|-------------|--------|
| Budget splits | Research-weighted | - | Saturation.io, Wrapbook, Celtx, Women in Film & Video DC |
| Payroll fringe | 28% | 27–32% (union); 0% non-union | IATSE 2026–2028 tiers |
| Tax credit | 30% | 0–40% | NY 30%; NJ 30–40% on qualified spend, transferable |
| Distribution fee | 20% | 20–35% of gross | Industry standard |
| Sales agent fee | 10% | 10–20% of gross | Industry standard |
| Investor recoupment premium | 120% | 110–125% | Industry standard |
| Net profit split | Investor 50 / Producer 30 / Talent 15 / Contributors 5 | - | Standard 50/50 financier/creative split |

---

## Skills demonstrated

- **Financial modelling** - multi-stage recoupment waterfall, break-even analysis, equity reduction via tax credit
- **Industry research** - sourced and calibrated all defaults from US indie film market data
- **React (JSX)** - three connected engines sharing state via hooks (`useState`, `useMemo`); custom SVG chart components
- **UI/UX** - typed + slider input, out-of-range warnings, one-click normalisation, fully editable milestone tables
- **Deployment** - self-contained HTML delivery (all libraries embedded; no build pipeline needed to run or share)
- **Documentation** - full research citations, honest limitations, and clear next-steps scoping

---

## Honest limitations

The tool is intentionally scoped as an equity-only, single-gross-input planning model:

- No debt / gap financing tiers (production loans, mezzanine)
- No revenue by source (streaming vs theatrical vs international have different effective fee rates)
- No time dimension - no IRR, no payback period, no payment dates
- No scenario save and compare
- No multi-investor position stack (1st / 2nd / 3rd position)

---

## What's next

Natural extensions to build on this foundation:

1. **Scenario save & compare** - save named deal scenarios and view them side by side
2. **Revenue by source** - split gross into streaming / theatrical / international / other, each with its own fee rate
3. **Break-even sensitivity chart** - investor multiple plotted across a range of gross revenues
4. **Investor position stack** - model 1st / 2nd / 3rd position investors with different recoupment priorities
5. **Timeline + IRR** - add dates to milestones and revenue arrivals, compute payback period and internal rate of return
6. **On-chain contract generation** - use the simulator's outputs to generate real smart contract parameters for deployment

---

## File structure

```
pay-out-simulator/
├── index.html      # The full simulator - open this in any browser
└── README.md
```

`index.html` is fully self-contained: React, ReactDOM, and all chart components are embedded directly in the file. It works from a hosted URL or downloaded locally - no internet connection required at runtime, no install, no build step.

---

## Context

Built during the [Lunim Intelligence](https://lunim.io) Finance & AI Analyst internship as the Capstone project. Lunim is building a creative collaboration platform combining AI-powered discovery, smart contracts, and transparent revenue splits for the independent film industry.

The tool directly addresses one of Lunim's core problems: *deals are vague, fragile or unenforceable.* Making the full economics visible before anyone signs helps creators walk into a pitch investor-ready, and gives both sides the confidence to commit.

---

*Diana Zagrebina - Finance & AI Analyst Intern, Lunim Intelligence, 2026*
