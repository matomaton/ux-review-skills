---
name: "tog-principles-review"
description: "Deep evaluation of an interface against Bruce Tognazzini's First Principles of Interaction Design, focused on human-in-the-loop review of AI and data-heavy output."
---

# Tog's First Principles Review (Deep)

Evaluate a design against Bruce "Tog" Tognazzini's First Principles of Interaction Design (asktog.com/atc/principles-of-interaction-design). Tog's lens is the **interaction contract**: interfaces should be visually apparent and forgiving, give users a sense of control, keep cognitive load low, hide system complexity the user doesn't need, and never lose work.

This lens complements nielsen-heuristics-review (usability) and laws-of-ux-review (perception and cognition). It goes deeper on **control, state, latency, defaults, and protecting work**, which is where AI review tools most often fail.

---

## Inputs
- **Artifact:** screenshot, Figma link, HTML, flow, prototype, or spec
- **Context:** user role, the decision being made, data volume, frequency of use, time pressure, and consequence of error
- **Mode:** `quick` (top principles only, 1 page) or `deep` (all principles with sub-checks). Default to `deep`.
- If context is missing, state assumptions in one line and proceed

## The AI-output lens
Ask these throughout, not just in one section:
- **Provenance** — Is it obvious what the model produced vs. source data vs. human edits?
- **Confidence** — Is uncertainty shown, and is it honest and readable?
- **Verification cost** — How many steps to check a claim against its source?
- **Automation bias** — Does the design make rubber-stamping the easiest path?
- **Reversibility** — What happens after a human acts on a wrong output?
- **Human authority** — Does the AI suggest, or does it quietly decide?

---

## The principles

For each principle: the core idea, sub-principles to test, review checks, and AI-specific checks.

### 1. Aesthetics
**Core:** Visual design serves usability; fashion never overrides it.
- Visual design should be done by trained visual designers, not left to chance
- Trend-driven choices (flat, low-contrast, hidden controls) must not cost clarity
- Visual changes get user-tested like behavioral changes

**Check:** Does styling reduce legibility, affordance, or contrast anywhere? Has the visual layer been tested, or only the flow?
**AI check:** Does polish make AI output look more authoritative or final than it is?

### 2. Anticipation
**Core:** Bring every tool and piece of information the user needs for each step to them, without making them leave the screen.
- Requires real understanding of the task, not assumptions
- A tool users can't find effectively doesn't exist

**Check:** Map the decision on this screen. Is every input to that decision present or one action away? Count context switches per decision.
**AI check:** Is the source evidence (records, readings, documents) beside the AI claim? Are related items, history, and prior decisions anticipated?

### 3. Autonomy
**Core:** The workspace belongs to the user. They make their own choices, even inefficient ones.
- Give users enough status information to make informed decisions
- Responsible control remains the designer's job (readable minimum text size, sensible timing)
- Don't trap users in a single prescribed path

**Check:** Can users choose order, filter, sort, and pace? Are there forced sequences that don't need to be forced?
**AI check:** Can users override, edit, reject, or ignore AI output? Is any automated action taken without the human knowing? Who has final authority, visibly?

### 4. Color
**Core:** Color is a vital channel; never the only channel.
- **Color blindness:** always pair color with a secondary cue (text, icon, shape, position, pattern)
- Test with color-blindness simulation
- Don't strip meaningful color for trend reasons

**Check:** Grayscale the screen. Can status, severity, and selection still be read?
**AI check:** Are confidence levels, anomaly flags, and approve/reject states distinguishable without color?

### 5. Consistency
**Core:** Consistency is about matching user expectations, not visual uniformity.
Levels, from least to most critical:
1. Platform and in-house standards
2. Suite-level consistency
3. App-level look and feel
4. Small visible structures (icons, buttons, controls)
5. Invisible structures (behaviors, shortcuts, rules)
6. **Interpretation of user behavior** (most critical: the system must read user actions the way the user meant them)
- **Induced inconsistency:** things that behave differently must look different
- **Continuity** beats rigid uniformity across versions
- User expectations outweigh elegant internal logic

**Check:** Walk each level. Flag where same-looking things behave differently, or different-looking things behave the same.
**AI check:** Are AI-generated elements marked the same way everywhere? Does an AI suggestion look different from a confirmed record? Does "approve" mean the same thing in every queue?

### 6. Defaults
**Core:** Defaults should be smart and trivially replaceable.
- Defaults must be easy to "blow away" (select-all on focus, easy clear)
- Only provide a default when there's a clear winner
- Replace vague "Default" labels with what the setting actually does
- Make the scope of reset actions visually obvious

**Check:** List every pre-filled value and pre-selected option. Is each one earned?
**AI check:** Is AI output pre-filled as the answer, or pre-selected as approved? Treat a default that commits a consequential decision as **severity 3+**. Is AI-filled content visually distinct from user-entered content?

### 7. Discoverability
**Core:** Hiding complexity often increases it. If users can't find a function, it doesn't exist.
- Keep needed controls visible unless screen size truly forbids it
- Use active discovery: surface advanced features progressively, in context, over time

**Check:** Can a first-time user find override, flag, export, undo, and help without instruction? List hidden controls (hover-only, overflow menus, gestures).
**AI check:** Can reviewers find how to trace an output to its source, see why the model said it, and report a bad result?

### 8. Efficiency of the User
**Core:** Optimize human productivity, not machine efficiency.
- Waiting users are wasted labor cost; keep them productive
- Architecture (task flow, data model) matters more than surface tweaks
- Error messages state the problem, the fix, and allow that the system may be at fault

**Check:** Estimate actions per item reviewed and time per decision. Where does the user wait, re-enter, or re-find?
**AI check:** Are batch actions, keyboard review, and confidence filtering available? Does efficiency come at the cost of judgment (one-click approve-all)?

### 9. Explorable Interfaces
**Core:** Provide clear paths, but let users wander safely.
- Make actions reversible; always support undo
- Provide stable landmarks so users can find their way back
- Give clear cues for where a workflow begins and ends

**Check:** Which actions are irreversible? Is there preview, compare, or sandbox before commit?
**AI check:** Can users compare AI output to alternatives, re-run with different inputs, or see what changes if they accept? Can approvals be reverted?

### 10. Fitts's Law
**Core:** Acquisition time depends on target size and distance.
- Large, near targets for frequent actions
- Screen edges and corners are high-value targets on pointer devices
- Applies to touch as well as mouse

**Check:** Measure target sizes and travel distance for the primary loop. Are destructive actions far from frequent ones?
**AI check:** In a review loop, are approve / reject / flag close to the content being judged, and not adjacent to each other in a way that invites misclicks?

### 11. Human Interface Objects
**Core:** Interface objects must be perceivable and behave consistently with what they appear to be.
- Objects can be seen, heard, or felt; their identity should be clear
- If behavior differs, create a new object rather than overload an existing one

**Check:** Inventory the object types on the screen. Does each have a clear identity and predictable behavior?
**AI check:** Are "AI suggestion," "source record," "human-confirmed fact," and "system alert" distinct objects with distinct behaviors?

### 12. Latency Reduction
**Core:** Hide latency where possible; communicate it where not.
- Use background processing so users can keep working
- Acknowledge every click or tap within ~50 ms
- Show clear progress during longer waits
- Remove unnecessary elements to speed responses

**Check:** Identify every wait. Is there instant acknowledgement, progress feedback, and a way to keep working?
**AI check:** During model runs or data syncs, is status visible, partial output labeled as partial, and the rest of the UI usable? Is stale data timestamped?

### 13. Learnability
**Core:** Decide whether learnability or long-term usability matters more, based on frequency of use.
- High-frequency tools favor expert efficiency; occasional tools favor learnability
- Test long-term proficiency, not just the first-use curve

**Check:** Classify frequency of use. Is the design optimized for the right end?
**AI check:** Do new reviewers learn what confidence means and how to verify? Do experts get accelerators?

### 14. Metaphors
**Core:** Pick metaphors that convey the right conceptual model; abandon them when they constrain.
- Use sensory cues to make the metaphor coherent
- Drop a metaphor when it starts lying

**Check:** List the metaphors and terms in use. Does each imply something true?
**AI check:** Watch for false metaphors: "verified" when only processed, "insight" when only correlation, "assistant" that acts without asking.

### 15. Protect Users' Work
**Core:** Users must never lose work to errors, crashes, timeouts, or navigation.
- Forms keep input through validation errors
- Continuous save is the standard

**Check:** Simulate refresh, timeout, back button, validation failure, and network loss. What survives?
**AI check:** Do reviewer edits, annotations, and decisions survive a model re-run, a data refresh, or a regenerate? Does regenerate overwrite human edits?

### 16. Readability
**Core:** Text must be legible.
- High contrast text; avoid low-contrast gray on gray
- Font sizes suited to the real display and real users

**Check:** Check contrast ratios (WCAG AA minimum) and minimum text sizes, especially in dense tables.
**AI check:** Are long AI outputs scannable (headings, highlights, citations) rather than walls of text?

### 17. Simplicity
**Core:** Simplicity is not the absence of capability; it's the absence of unnecessary complexity for the user.

**Check:** What could be removed without losing a decision input? Is complexity carried by the system or pushed onto the user?
**AI check:** Is the AI adding steps (review screens, explanations) that don't change decisions, or removing steps that should stay human?

### 18. Track State
**Core:** Remember where the user was and what they did.
- Persist position, filters, selections, and progress across sessions

**Check:** Leave and return. Is the user back where they were?
**AI check:** Is reviewed vs. unreviewed vs. changed-since-review visible? Is the version of the AI output the user approved recorded?

### 19. Visible Navigation
**Core:** Users should always know where they are and how to get back.
- Minimize deep or hidden navigation

**Check:** From any screen, can the user name their location and return to the start in one action?
**AI check:** In drill-downs from AI summaries to source detail, is the path back obvious and position preserved?

---

## Severity scale (shared 0–4)
- **0** Not a problem
- **1** Cosmetic — fix if time allows
- **2** Minor — low priority
- **3** Major — users will struggle or make wrong calls
- **4** Catastrophe — likely to cause harmful or costly decisions; fix before release

**Escalate one level** when the issue weakens human judgment over AI output: lost autonomy, consequential defaults, hidden state, lost reviewer work, or indistinguishable AI vs. source content.

---

## Process
1. **Interaction job:** one sentence — *who acts, on what output, with what consequence*
2. **Classify use:** frequency (daily / weekly / occasional) and stakes (low / medium / high)
3. **Walk the principles** in order. In `deep` mode, test every sub-check. Mark "No issues observed" or "Not applicable" briefly when true.
4. **Cite evidence** for every finding: element, label, state, or flow step
5. **Recommend** a buildable fix for every finding
6. **Rank** the top 3 fixes by severity × frequency
7. **Note open questions** where the artifact doesn't show enough to judge

## Output format

**Interaction job:** one sentence

**Use profile:** frequency · stakes · primary user

**Assumptions:** bullets, only if needed

| # | Principle | Sub-check | Finding | Evidence | Severity | Recommendation |
|---|-----------|-----------|---------|----------|----------|----------------|

**Top 3 fixes**
- **Fix** — why it matters, expected effect

**Strengths worth keeping**
- 1–3 bullets

**Open questions**
- Things the artifact doesn't show that would change the rating

## Rules
- Candid, specific, evidence-based; praise only what's earned
- One problem per row
- Don't invent elements you can't see; ask about gaps
- Paraphrase Tog's principles; don't quote the source at length
- Use the shared severity scale so results merge with nielsen-heuristics-review and laws-of-ux-review