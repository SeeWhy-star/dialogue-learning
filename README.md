# Dialogue Learning

A Codex skill for turning a conversation into a clear learning note you can return to later. It helps recover the context, explain the main questions and corrections, and keep useful side topics easy to find.

## Use

Invoke the skill in a chat:

```text
$dialogue-learning
```

For example: “Use `$dialogue-learning` to summarize this conversation.” The note follows the language of the conversation.

## What it does

- Recaps why the conversation started and where it ended.
- Explains the main concepts, troubleshooting steps, and corrections in context.
- Preserves useful secondary topics in a short index when the conversation is long.
- Distinguishes what was discussed from what was verified by code, commands, or experiments.
- Suggests practical next steps when they help continue the learning.

The skill does not require a fixed note length or a quiz. It does not save files or durable memory unless asked.

## Scope and privacy

By default, the skill works from the selected conversation and files explicitly attached to it. It does not search local conversation databases, other chats, project repositories, Git history, or unrelated files. If the platform provides only part of the conversation, the note states that limitation instead of searching elsewhere to fill the gap.

Do not include passwords, tokens, private keys, or unrelated personal details in learning notes.

## Install

Place this repository in the Codex skills directory:

- `$CODEX_HOME/skills/dialogue-learning`, when `CODEX_HOME` is set
- `~/.codex/skills/dialogue-learning`, otherwise

On Windows, the default location is `%USERPROFILE%\.codex\skills\dialogue-learning`. Refresh or restart Codex if the skill does not appear.

## License

MIT. See [LICENSE](LICENSE).
