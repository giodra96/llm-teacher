# LLM Teacher

LLM Teacher is a lightweight agent skill that turns ordinary work and questions into learning opportunities. It helps an agent explain meaningful decisions, track concepts in the current workspace, and quiz the user on topics that need reinforcement.

The task still comes first: the skill explains important reasoning and reusable ideas without narrating every command or overwhelming the user.

## Core behavior

- Teach concepts in the user's language while keeping persisted data in English.
- Explain design choices and trade-offs during substantive development work.
- Track only meaningful, reusable topics in `.llm-teacher.yml`.
- Distinguish exposure from demonstrated understanding.
- Mark weak points only from evidence provided by the user.
- Run short adaptive quizzes, with progressive hints when requested.

## Workspace memory

Tracking is local to the current workspace and disabled until initialized:

```text
.llm-teacher.yml
```

The file contains preferences, topic mastery, concise weak points, and minimal learning notes. It does not store complete conversations or source code and is ignored by Git by default.

## Usage

Use natural language so the same prompts work across compatible agents:

```text
Use the llm-teacher skill to initialize learning in this workspace.
Use the llm-teacher skill while implementing this feature.
Quiz me on the topics I am weakest at.
Give me a hint quiz about database transactions.
Show my learning progress.
```

Host-specific invocation shortcuts may also work, but they are not required. Once initialized, compatible agents can use the skill automatically for substantive learning and development tasks in that workspace.

## Skill layout

```text
SKILL.md
references/learning-memory.md
references/quiz-workflow.md
```

The small entrypoint routes only memory and quiz requests to their focused references. The skill intentionally has no product-specific metadata, runtime dependencies, or helper scripts.

## Scope

Learning state is not shared automatically across workspaces, machines, or cloud sessions. When persistent workspace storage is unavailable, the agent can still teach and quiz without claiming to remember previous sessions.
