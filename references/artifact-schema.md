# Artifact schema

Use one Markdown file per durable artifact when the knowledge base is large, or grouped files when it is small. Every artifact has a stable ID and these fields:

```yaml
id: concept-path-001
type: concept | question | error-lesson | decision | procedure | exercise
title: concise human-readable title
status: observed | proposed | verified | partial | unresolved | superseded
mastery: unknown | recognition | explanation | guided-use | independent-use
source:
  session: session identifier or date
  turns: turn numbers, message IDs, or transcript lines
  evidence: command output, document, experiment, or user confirmation
confidence: low | medium | high
related: []
review:
  next: YYYY-MM-DD
  attempts: 0
```

The Markdown body should use only the sections relevant to the type:

## Concept

- **In my words**: explanation a learner could say without copying the AI.
- **Why it matters**: where it changes a decision.
- **Example**: a concrete case from the conversation.
- **Boundary**: when it does not apply.
- **Teach-back**: one explanation or prediction prompt.

## Question

- **Original question**
- **Current answer**
- **What would count as evidence**
- **Remaining uncertainty**
- **Next check**

## Error lesson

- **Observed symptom**
- **Attempt and result**
- **Wrong or incomplete assumption**
- **Likely cause**
- **Verification steps**
- **Reusable detection signal**
- **Prevention**

## Decision or procedure

- **Context and constraints**
- **Chosen approach**
- **Alternatives considered**
- **Reason and evidence**
- **Reproduction steps**
- **Rollback or failure condition**

## Exercise

- **Prompt**
- **Expected evidence of understanding**
- **Answer** (keep hidden during a quiz)
- **Follow-up difficulty**

Never fill `evidence` with confidence alone. If an item comes only from an AI explanation, set `status: proposed` or `partial` and create a verification task.
