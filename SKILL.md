---
name: dialogue-learning
description: >-
  Turn human-AI conversation history into traceable learning artifacts:
  concepts, solved and unsolved questions, error lessons, decisions,
  verification tasks, and review prompts. Use when the user asks to learn
  from a conversation, preserve useful history, review past work, or reduce
  dependence on repeated AI answers.
---

# Dialogue Learning

Treat the conversation as a learning record, not as disposable chat. The output must help the user understand, verify, recall, and eventually perform relevant work without the transcript.

## Choose a mode

- **Capture**: extract the current conversation when the user says to save, learn from, or distill it.
- **History**: inspect an available conversation export or history tool, then process sessions in bounded chunks. Never pretend to have read history that is not available in the current environment.
- **Review**: quiz the user from saved items. Ask for an explanation or prediction before revealing the answer; grade the explanation and update mastery.
- **Distill**: compare several saved sessions, merge duplicates, resolve contradictions, and promote only repeatedly useful knowledge to durable project or personal rules.

If the user did not choose a mode, use Capture for the current conversation and offer Review for the most important gaps.

## Capture workflow

1. Identify the user's goal, starting understanding, concrete outcomes, and important corrections.
2. Separate observations from interpretations. Record claims from the AI as hypotheses until supported by a command, document, experiment, or user confirmation.
3. Extract only durable material into the schema in [references/artifact-schema.md](references/artifact-schema.md): concepts, questions, error lessons, decisions, procedures, and exercises.
4. For each artifact, include a short source pointer to the conversation turn or transcript location. Preserve the original transcript separately when available.
5. Mark what is solved, partially understood, unverified, contradicted, or still open. Do not convert a plausible explanation into a fact.
6. Create at least one teach-back or prediction prompt for each important new concept or recurring error. Prefer a small practical task over a recall-only question.
7. Present a compact draft for user confirmation before writing durable memory, project rules, or global instructions. A summary may be shown without confirmation; durable writes require confirmation.

## Learning quality rules

- Do not reward passive agreement. Ask the user to explain the cause, predict an outcome, or choose a diagnostic step before giving the explanation.
- Distinguish “the task was completed” from “the user can reproduce it.” Track both separately.
- Preserve failed attempts. The failed assumption, observed signal, and correction are often more reusable than the final command.
- Link related questions and concepts instead of repeating them in every session.
- When sources conflict, show the conflict and propose a verification step; never silently pick one.
- Keep personal preferences separate from technical facts and project-specific rules.
- Avoid saving secrets, tokens, private credentials, or unnecessary personal data from transcripts.

## Output and storage

Use a user-selected knowledge directory. If none exists, propose `knowledge/` in the active project for project material and a separate user directory for personal learning. Keep these layers distinct:

- raw transcript or source pointer
- session record
- durable artifacts
- review history and unresolved questions

Use readable Markdown with stable IDs so later sessions can cite and update an artifact. Do not silently edit existing durable entries: show the proposed merge, correction, or retirement first.

## Commands expressed in natural language

Recognize requests equivalent to: “提炼这次对话”, “整理我的错误”, “我真的学会了吗”, “复习最近的知识”, “找出还没解决的问题”, “把这些对话合并成知识库”, and “这个结论的来源是什么”. Respond with the appropriate mode and keep the interaction focused on learning outcomes rather than producing a longer transcript summary.
