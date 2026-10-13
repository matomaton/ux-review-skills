---
name: "laws-of-ux-review"
description: "Evaluate an interface against the Laws of UX (cognitive, perceptual, and behavioral principles), tuned for dense data and AI-output review screens."
---

# Laws of UX Review

Evaluate a design using the Laws of UX collection (Jon Yablonski). This lens focuses on **how people perceive, think, and decide**, which matters most when the screen is dense with data or machine output and the human must judge it.

## Inputs
- The artifact: screenshot, Figma link, HTML, flow, or spec
- Context: user role, decision, volume of items, time pressure, consequence of error
- If context is missing, state assumptions in one line and proceed

## The AI-output lens
Pay special attention to:
- **Cognitive load** of comparing AI output with source data
- **Selective attention** — will anomalies and low-confidence items actually be noticed?
- **Cognitive bias** — does the design amplify automation bias, anchoring on the AI's answer, or confirmation bias?
- **Aesthetic-usability effect** — does polish make output look more trustworthy than it is?

## How to apply
Don't force all 30 laws onto every screen. Triage first, then go deep.

### Step 1 — Triage
Scan the list and pick the laws that are **materially relevant** to this screen (usually 8–14). List the ones skipped in one line.

### Step 2 — Evaluate the relevant laws

**Perception and grouping (Gestalt)**
- **Law of Proximity** — Related items are near each other
- **Law of Common Region** — Shared boundaries group content (cards, panels)
- **Law of Similarity** — Similar-looking elements are read as related
- **Law of Uniform Connectedness** — Visually connected elements read as related
- **Law of Prägnanz** — People read complex visuals in the simplest form; keep charts and layouts unambiguous
- **Von Restorff Effect** — The distinct item gets noticed; reserve it for what truly matters (anomalies, low confidence)

**Cognition and memory**
- **Cognitive Load** — Total mental effort required; reduce extraneous load
- **Working Memory** — Users hold only a few items at once; keep comparisons on-screen
- **Miller's Law** — Chunk information rather than rely on memorizing long lists
- **Chunking** — Group information into meaningful units
- **Serial Position Effect** — First and last items are remembered best; place critical items accordingly
- **Selective Attention** — Users filter out what seems irrelevant, including banner-like warnings
- **Mental Model** — Match how users believe the system and domain work
- **Cognitive Bias** — Identify biases the design may trigger or mitigate

**Decision and action**
- **Hick's Law** — More choices, longer decisions; simplify the action set
- **Choice Overload** — Too many options paralyze; offer good defaults and filtering
- **Fitts's Law** — Target size and distance govern speed and accuracy
- **Doherty Threshold** — Responses under ~400ms keep users productive; communicate longer waits
- **Goal-Gradient Effect** — Motivation rises near completion; show queue progress
- **Zeigarnik Effect** — Unfinished tasks stick; surface incomplete reviews clearly
- **Flow** — Support focused, uninterrupted work; minimize context switching
- **Paradox of the Active User** — Users skip instructions; design for learning by doing

**Expectations and complexity**
- **Jakob's Law** — Users expect your product to work like others they know
- **Tesler's Law** — Some complexity is irreducible; decide whether the system or the user carries it
- **Occam's Razor** — Prefer the simplest design that does the job
- **Pareto Principle** — Focus on the 20% of features and items that drive 80% of value or risk
- **Postel's Law** — Be liberal in what you accept from users, conservative in what you output
- **Parkinson's Law** — Tasks expand to fill time; reduce steps, autofill sensibly
- **Aesthetic-Usability Effect** — Attractive designs are perceived as more usable and more credible
- **Peak-End Rule** — Experiences are judged by their peak and their end; get the completion moment right

### Step 3 — Synthesize
Group findings into the four themes above and rank the top 3 fixes.

## Severity scale (shared 0–4)
- **0** Not a problem · **1** Cosmetic · **2** Minor · **3** Major · **4** Catastrophe

Raise severity one level when the issue makes it likelier that a user misses an AI error or anomaly.

## Output format

**Screen job:** one sentence

**Laws applied:** list · **Skipped:** list with one-line reason

| # | Law | Theme | Finding | Evidence | Severity | Recommendation |
|---|-----|-------|---------|----------|----------|----------------|

**Top 3 fixes**
- **Fix** — why it matters, expected effect

**Strengths worth keeping**
- 1–3 bullets

## Rules
- Evidence over theory: name the element, don't just name the law
- One problem per row
- Don't invent unseen elements; ask about gaps
- Use the shared severity scale so results merge with nielsen-heuristics-review and tog-principles-review