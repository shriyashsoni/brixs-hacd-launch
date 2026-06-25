# Brixs Chain ($BRIXS) - Lovable Demo Prompt & Sprint Plan

## 1. Scope summary
- **Concept**: Brixs Chain ($BRIXS) is a Unified Liquidity L2/L3 tailored specifically for Emerging Markets.
- **Category**: Utility
- **Why HACD**: BRIXS natively forms its tokens on the HACD Stack rather than deploying a VC-controlled contract. A user's formation moment proves decentralized asset generation for network testnet fees. 
- **The formation moment**: A user stakes HAC, views the sub-cent gasless transaction confirmation (mocked via Account Abstraction), and receives a durable HACD Stack record confirming they are an early network participant.
- **PoW-fit read**: Strong. The testnet requires gasless transactions, and the HACD Stack provides the perfect decentralized bootstrapping mechanism without VC lockups.

## 2. Executive Lovable prompt

```text
You are a senior full-stack product engineer. Build a working, demo-ready web
app for the HACD Labs Incubator Cohort 2 sprint. Optimize for a single,
one-minute-legible formation moment over feature breadth.

# Product
Brixs Chain — A Unified Liquidity L2/L3 tailored for Emerging Markets with gasless onboarding.
Category: utility.

# Why HACD (do not break this framing)
This product issues a HACD Stack Asset: it is FORMED, not merely deployed —
HACD is the PoW container, HAC pays the stack cost, and Stack is the formation
action that writes durable on-chain state. A regular L2 token could be minted arbitrarily by a central team; BRIXS tokens are formed via HACD to guarantee fair, verifiable initial distribution. Treat each formed HACD as a "formation record" whose formation time cannot be backdated. Never imply stack cost guarantees a price, and never call HACD "merely an NFT".

# Scope for the sprint
In scope:
- Unified L2 liquidity dashboard overview
- Gasless transaction simulation
- The formation moment: A user forms BRIXS by staking HAC and receives a formation receipt.
Out of scope (explicitly skip): real wallet/payment signing, auth beyond a mock
sign-in, mobile-native apps, and active mainnet deployment. If a live HACD connection is unavailable, mock the Stack / formation step faithfully and label it "formation: mocked for demo" in the UI.

# Pages / screens
- Dashboard: Overview of Brixs L2 ecosystem metrics (mocked).
- Formation Page: The core action where a user stakes HAC to form BRIXS.
- Formation Receipt: The post-formation proof view showing the formed-at time and cost.

# Data model
- L2Transaction { id, type, gasFee, status }
- HacdStackRecord { hacdName (16-letter alphabet), formedAt, stackCostHac, status ("formed" | "mocked"), l2ParticipationTier }

# HACD integration points
- On the Formation Page, when a user clicks "Form BRIXS", a HacdStackRecord is created and displayed as a receipt with its formed-at time.
- The Dashboard displays recent formation proofs.
- The user's participation tier is derived from the number of lots they formed.

# The formation moment (build this first and polish it most)
A reviewer signs into the mock dashboard, navigates to the "Participate" tab, and initiates a formation of 1 lot (1,000,000 BRIXS units). They see the transaction confirmed gaslessly (via Account Abstraction), followed by a HACD Stack receipt proving their formation timestamp and the 50 HAC stack cost.

# Visual system
Dark, editorial, "terminal-confident" aesthetic:
- Background #14151A; cards #1C1D24 (hover #212229); borders #2A2B33.
- Text: primary #EDEAE3, secondary #9A9CA6, muted #65676F.
- Category accents: Utility #6FB3AB. Use this product's category accent for
  links, active states, and the formation highlight.
- Fonts: 'Space Grotesk' for headings, 'Inter' for body, 'JetBrains Mono' for
  labels, tickers, the HACD name, stack cost, and the formation timestamp.
- Rounded 14px cards, subtle 3px translate-up on hover, monospace metadata rows.
- Respect prefers-reduced-motion.

# Acceptance criteria (the build is done when)
- [ ] A user can complete the formation moment end to end.
- [ ] A HacdStackRecord is created and its formation time is shown.
- [ ] Formation proof is visible to a second viewer (the reviewer's POV).
- [ ] The why-HACD value is obvious from the UI without explanation.
- [ ] Mocked vs. live formation status is labeled honestly.
- [ ] No price-floor, yield, guaranteed-return, or "merely an NFT" language.
- [ ] The app runs with no console errors and matches the visual system.

Use mock/local data so the app runs immediately. Keep the code clean and the README short.
```

## 3. Sprint plan

- **20 June**: **Lock scope.** Confirm concept, category, why-HACD, and the single formation moment. Apply at `hacd.it/incubator`.
- **21 June**: **Scaffold.** Generate the app in Lovable from the executive prompt. Get the core page and data model rendering with mock data.
- **22 June**: **HACD integration.** Wire the Stack / formation flow (faithfully mocked and labeled) so a HACD formation record is created and displayed.
- **23 June**: **The formation moment.** Build and polish the gasless formation receipt flow.
- **24 June**: **Polish + proof.** Apply the visual system, capture a short demo video or screenshots.
- **25 June**: **Pair with issuance.** Package with the 8 generated issuance documents. Run `python3 scripts/validate_launch_spec.py project_brixs/launch_spec.json --strict`.
- **26-27 June**: **Launch + submit.** Final submit before the 27 June deadline, publish the Lovable share link, and wait for the 29 June winners announcement.

## 4. Submission link-up

This demo build pairs with the generated 8-document issuance package in the `project_brixs` folder. Make sure to include this demo link when submitting the final package to HACD Labs, alongside the validated `launch_spec.json`.

This is a draft demo build prompt for review. Pair it with the validated 8-document issuance package. Final Launchpad parameters must be confirmed by the issuer and HACD Labs before publication.
