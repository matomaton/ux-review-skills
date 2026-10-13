---
name: "nielsen-heuristics-review"
description: "Evaluate a UI, flow, or screenshot against Nielsen's 10 usability heuristics, with extra scrutiny for screens where people review and act on AI output."
---

# Nielsen Heuristics Review

A heuristic evaluation using Jakob Nielsen's 10 usability heuristics. Built for interfaces where a human must **understand, judge, and act on** machine output: AI summaries, sensor/grid telemetry, inventory reconciliation, generated content awaiting approval.

## Inputs
- The artifact: screenshot, Figma link, HTML, flow description, or written spec
- Context, if known: primary user (role, expertise), the decision they make on this screen, and the cost of getting it wrong
- If context is missing, state your assumption in one line and proceed

## The AI-output lens
For every heuristic, also ask:
- **Provenance** — can the user tell what the AI produced vs. what is source data?
- **Confidence** — is uncertainty shown, and shown honestly?
- **Verification cost** — how many steps to check a claim against its source?
- **Automation bias** — does the design invite rubber-stamping?
- **Reversibility** — what happens after the user acts on a wrong output?

## The 10 heuristics
1. **Visibility of system status** — Is it clear what the system is doing, has done, and how fresh the data is? (Model running, data as-of timestamp, partial results, stale sensor feeds.)
2. **Match between system and the real world** — Does it use the user's vocabulary, not the model's or the database's? Are units, categories, and confidence expressed in domain terms?
3. **User control and freedom** — Can users undo, override, reject, or edit AI output? Is there an exit from an automated path?
4. **Consistency and standards** — Are AI-generated elements marked the same way everywhere? Do patterns follow platform and design-system conventions?
5. **Error prevention** — Does the design stop high-cost mistakes before they happen? (Confirmation on bulk-approve, guardrails on low-confidence items, constraints over warnings.)
6. **Recognition rather than recall** — Is the source evidence shown next to the claim, or must users remember or go find it?
7. **Flexibility and efficiency of use** — Are there accelerators for experts (keyboard review, batch actions, filters by confidence) without burdening novices?
8. **Aesthetic and minimalist design** — Does every element earn its place? Is signal (anomalies, disagreements, low confidence) visually louder than noise?
9. **Help users recognize, diagnose, and recover from errors** — When AI is wrong or a pipeline fails, is the message plain, specific, and paired with a next step?
10. **Help and documentation** — Is there just-in-time explanation of how outputs were produced and what confidence means?

## Severity scale (Nielsen 0–4)
- **0** Not a problem
- **1** Cosmetic — fix if time allows
- **2** Minor — low priority
- **3** Major — high priority; users will struggle or make wrong calls
- **4** Catastrophe — must fix before release; likely to cause harmful or costly decisions

Raise severity one level when the issue increases the chance a user acts on wrong AI output without noticing.

## Process
1. Restate the screen's job in one sentence: *who decides what, based on which output*
2. Walk the 10 heuristics in order; skip none, but write "No issues observed" when true
3. Cite **specific evidence** for each finding (element, label, state) — no generic critique
4. Pair every finding with a concrete, buildable recommendation
5. Finish with the top 3 fixes ranked by severity × frequency

## Output format

**Screen job:** one sentence

**Assumptions:** bullets, only if context was missing

| # | Heuristic | Finding | Evidence | Severity | Recommendation |
|---|-----------|---------|----------|----------|----------------|

**Top 3 fixes**
- **Fix** — why it matters, expected effect

**Strengths worth keeping**
- 1–3 bullets

## Rules
- Be candid and specific; praise only what is earned
- Do not invent screen elements you can't see; flag gaps as questions
- Keep findings atomic: one problem per row
- When run alongside tog-principles-review or laws-of-ux-review, use the same severity scale so findings can be merged