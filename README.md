# LLM Teacher

LLM Teacher is a lightweight agent skill that helps users learn while getting things done. When active, it accompanies the requested result with a teacher-style explanation of the tools used, the reasons for key choices, and the steps that led to the solution.

The goal is to help users evaluate the work, reuse the method, and become more independent. Explanations stay proportional to the task and use the user's language and level of familiarity.

## Core behavior

- Complete the user's request and keep the result easy to find.
- Explain what the tools and techniques do and why they fit the task.
- Describe the criteria, evidence, and trade-offs behind important decisions.
- Summarize the path to the solution and explain how the result was checked.
- Highlight a practical idea or method the user can apply next time.

There are no quizzes, learning records, or saved preferences. No initialization or workspace configuration is required.

## Usage

Use natural language so the same prompts work across compatible agents:

```text
Use the llm-teacher skill while implementing this feature.
Fix this bug and explain the tools, choices, and checks so I can learn the method.
Use llm-teacher to compare these options and explain the criteria behind your recommendation.
```

Host-specific invocation shortcuts may also work, but they are not required. Ask for a shorter explanation, more detail, or just the result whenever needed.

## Skill layout

```text
SKILL.md
```

The skill is self-contained in `SKILL.md`, with no runtime dependencies, helper scripts, or persistent state.
