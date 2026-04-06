---
name: analyze-document
description: This skill should be used when the user asks to "analyze a document", "extract insights", "deep read", "what are the insights in this file", or wants more than a summary from a document. It reads a document and applies a structured analytical framework that surfaces non-obvious insights, tensions, actionable takeaways, and gaps — instead of producing a generic summary.
allowed-tools: Read, Glob, Grep
---

# Analyze Document

**Purpose**: Apply a structured analytical framework to any document, extracting non-obvious insights, tensions, actionable implications, and gaps — going far beyond a generic summary.

## Usage

```
/analyze-document <file-path>
```

If no file path is provided, ask the user which document to analyze.

## Instructions

### Step 1: Read the Document

1. Read the target document using the provided file path
2. If the file has YAML frontmatter, note the `type` field for document-type detection in Step 3

### Step 2: Apply the Core Analysis Framework

Analyze the document using these four lenses. Present each as its own section with clear findings:

#### 1. Non-Obvious Insights (3-5)

Identify things that aren't stated explicitly but can be inferred from the content. Skip anything the author already highlights as a key point. Look for:
- Patterns that emerge across sections
- Second-order implications of what's stated
- Connections the author doesn't draw explicitly
- What the emphasis or word choice reveals

#### 2. Tensions and Contradictions

Find where the argument conflicts with itself, or with conventional wisdom. Look for:
- Internal inconsistencies between sections
- Optimistic claims paired with cautious caveats
- Goals that conflict with stated constraints
- Assumptions that contradict evidence presented
- What's left unresolved

#### 3. The "So What" (Single Actionable Takeaway)

If a smart, busy person could only take away one actionable implication from this document, what would it be and why? Commit to a single, prioritized takeaway — not a list of equally weighted points.

#### 4. What's Missing

What question does this document raise but never answer? What would a reader want to know next? Look for:
- Unstated assumptions the argument depends on
- Evidence that would strengthen or weaken the claims
- Perspectives or stakeholders not represented
- Follow-up questions the document creates but doesn't address

### Step 3: Apply Document-Type Modifier

Based on the frontmatter `type` field or the document's content, add one additional analytical lens:

| Document Type | Additional Analysis |
|---|---|
| `meeting-notes`, transcripts | **Implicit decisions**: What decision was implicitly made but never explicitly confirmed? What did everyone seem to agree on without anyone formally stating it? |
| `research`, academic papers | **Methodological assumptions**: Flag any methodological choices that could meaningfully change the conclusions if done differently. What assumptions are baked into the approach? |
| `project`, `design-document`, `implementation-plan`, strategy docs | **Unstated dependencies**: Identify the strongest unstated assumption this plan depends on. What must be true for this to succeed that nobody is questioning? |
| `policy`, `rfc`, `adr` | **Edge cases and failure modes**: What scenarios would this policy/decision handle poorly? Where are the boundaries undefined? |
| News articles, industry reports | **Narrative framing**: What narrative is this constructing, and what facts would complicate or undermine it? |
| General / undetected | Skip the modifier — the core four lenses are sufficient. |

If the document type is ambiguous, make a best guess based on content and note the assumption.

### Step 4: Suggest Follow-Up Directions

After the analysis, suggest 2-3 specific follow-up questions the user could ask to drill deeper, such as:
- "Tell me more about tension #2"
- "What evidence would validate insight #3?"
- "How does the missing piece in #4 affect the 'so what'?"

## Output Format

```markdown
## Document Analysis: [Document Title]

**Document type**: [detected type]
**Source**: [[wikilink to original]]

### Non-Obvious Insights

1. **[Insight title]** — [Explanation with evidence from the document]
2. ...

### Tensions and Contradictions

1. **[Tension title]** — [What conflicts and why it matters]
2. ...

### The "So What"

[Single paragraph with the one actionable takeaway and why it matters most]

### What's Missing

1. **[Gap title]** — [What's unanswered and why it matters]
2. ...

### [Document-Type Specific Section Title]

[Findings from the type-specific modifier]

---

**Dig deeper:**
- [Follow-up question 1]
- [Follow-up question 2]
- [Follow-up question 3]
```

## Important Notes

- **Do not summarize.** The goal is analysis, not compression. Avoid restating what the document already says.
- **Be specific.** Reference particular sections, quotes, or data points from the document to support each finding.
- **Be opinionated.** Commit to claims rather than hedging with "it could be argued that..." — the user wants a sharp analytical lens, not equivocation.
- **Respect the vault.** Display the analysis in the conversation. Do not create new files unless the user asks to save the output.
