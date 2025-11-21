# KD — RFC Authoring Guide (PlayOn Sports)

## Purpose

Enable the model to draft **PlayOn Sports–style RFCs** that match our internal template, align to OKRs, and surface risks, ethics, and dependencies clearly—without inventing backend detail beyond a frontend-lead perspective.

## When to use

- The user asks to “write/draft/update an RFC,” “turn this plan into an RFC,” or “summarize a proposal for review.”
- Pair this KD with the **Exploratory TL** prompt. Prefer **Full Analysis** mode; convert its sections into the RFC fields below.

## Section mapping (Prompt → RFC)

- **Context Recap & Recommendation** → **Executive Summary** (goals, why it matters to PlayOn; mention OKR alignment).
- **Risks & Mitigations** (+ security/ethics) → **Ethical / Legal / Privacy Considerations** (bias, fairness, limitations, edge-case cautions).
- **Implementation Plan** (+ feasibility, deps) → **Proposed Implementation** and **Technical Feasibility / Required Data or Services** (prep work, cross-team coordination, service dependencies).
- **Options & Trade-offs** → **Alternatives** (other viable ways to reach the outcome).
- **Open Questions, Success Metrics, Next Steps** → **Follow up** (decision status, next steps) and **Reference files** (links to briefs, wireframes, diagrams).
- **Owners/Contributors** → fill **Owner, Contributors, Shared Service, Team Members**; set **Status** and **Decision**.

## Writing rules (make outputs consistent)

1. **PlayOn context first:** Tie problem/goals to OKRs in the Executive Summary.
2. **Ethics & privacy:** Call out bias/fairness risks, PII handling, reliability caveats, and any POC limitations explicitly.
3. **Feasibility & dependencies:** List required data/services, upstream/downstream teams, and any gating prep.
4. **Alternatives:** Give at least 2 credible options and say why they’re rejected vs. the proposed path.
5. **Artifacts:** Prefer **links** to design files, wireframes, and diagrams; embed simple ASCII diagram only if it clarifies.
6. **Status language:** Use the template statuses: **DRAFT / READY FOR REVIEW / APPROVED / CHANGE REQUESTED**.
7. **Scope discipline:** Keep frontend focus; if backend-heavy, add a brief “Frontend perspective…” note and stop.

## Validation checklist (run before finalizing)

- [ ] Executive Summary states goal, “why now,” and OKR linkage.
- [ ] Ethics/Legal/Privacy addresses bias/fairness, PII, limitations, and edge-case risks.
- [ ] Proposed Implementation names dependencies, prep work, and coordination points.
- [ ] Alternatives list ≥2 approaches with clear trade-offs.
- [ ] Follow-up includes decision status + concrete next steps.
- [ ] Reference files contain links to relevant artifacts (designs, briefs, diagrams).
- [ ] Metadata (Owner, Contributors, etc.) is filled or marked **TBD**.

---

## RFC Markdown skeleton (paste and fill)

```markdown
# RFC: <Title>

**Status:** DRAFT | READY FOR REVIEW | APPROVED | CHANGE REQUESTED  
**Owner:** <Name, Team>  
**Contributors:** <Names, Teams>  
**Shared Service:** <If applicable>  
**Team Members:** <Names>  
**Approved:** <Approver(s) or TBD>  
**Decision:** <DECIDED | IN REVIEW | OTHER>  
**Decision Status / Next Steps:** <Bullets with owners & dates>

## Executive Summary

- **Goal:** <What we’re achieving and why it matters to PlayOn>
- **OKR Alignment:** <Objective & Key Result IDs or descriptors>
- **Impact Snapshot:** <User, business, or platform impact in one or two bullets>

## Ethical / Legal / Privacy Considerations

- **Risks / Caveats:** <Edge cases, reliability constraints, unintended uses>
- **Bias & Fairness:** <Where bias could occur; how we detect/mitigate>
- **Privacy & Compliance:** <PII handling, data retention, consent, auditability>
- **POC Limitations:** <What the prototype cannot validate yet>

## Proposed Implementation

- **Approach Overview:** <One-paragraph outline; link to diagrams/wireframes>
- **Key Components:** <Frontend modules, flows, states>
- **Data & Services Needed:** <APIs, schemas, third-party services>
- **Coordination & Dependencies:** <Teams/services; blockers; sequencing>
- **Feasibility Notes / Prep Work:** <Experiments, migrations, prerequisites>

## Alternatives

- **Alt A:** <Summary> — **Pros:** <…> **Cons:** <…> — **Reason not chosen:** <…>
- **Alt B:** <Summary> — **Pros:** <…> **Cons:** <…> — **Reason not chosen:** <…>

## Follow up

- **Open Questions:** <Bulleted list>
- **Milestones & Owners:** <Dates, checkpoints, who’s accountable>
- **Rollout & Verification:** <Metrics, QA/UX validation, guardrails>

## Reference files

- [Design brief](link)
- [Wireframes](link)
- [System diagram](link)
```

---

## How the model should transform an Analysis into an RFC

1. Convert the **Executive Summary** from the problem statement + recommendation; include explicit **OKR** tags.
2. Move all security/ethics/privacy risks into the **Ethical / Legal / Privacy** section—don’t bury them elsewhere.
3. Collapse the **Implementation Plan** into “Approach / Components / Data & Services / Dependencies / Prep Work.”
4. Preserve **Alternatives** verbatim (trim to the top 2).
5. Collect **Open Questions**, **milestones**, and **verification metrics** under **Follow up**.
6. Insert links to artifacts under **Reference files**.
