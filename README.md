![LLM Teacher — Your agent, your teacher.](assets/llm-teacher_banner.png)

# LLM Teacher

LLM Teacher is a lightweight agent skill that helps users learn while getting things done. When active, it accompanies the requested result with a teacher-style explanation of the tools used, the reasons for key choices, and the steps that led to the solution.

The goal is to help users evaluate the work, reuse the method, and become more independent. Explanations stay proportional to the task and use the user's language and level of familiarity.

## Core behavior

- Complete the user's request and keep the result easy to find.
- Explain what the tools and techniques do and why they fit the task.
- Connect important decisions to concrete constraints and explain when an alternative would fit better.
- Teach through a worked example from the actual task, linking the steps to their purpose.
- Explain how the result was checked and, when feasible, how the user can repeat a check independently.
- Connect the example to a general principle and another situation where it applies.
- Adjust the support to the understanding demonstrated in the conversation.

There are no quizzes, learning records, or saved preferences. No initialization or workspace configuration is required.

The teaching approach draws on cognitive apprenticeship, worked examples, and connections between concrete and abstract representations. Local references contain concise source summaries, practical guidance, original examples, limitations, and bibliographic details. `SKILL.md` explains when to consult each reference; using them requires no web access. These adaptations are informed by learning research; their effectiveness in this skill has not been established, and receiving an explanation is not proof of independent ability.

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
references/cognitive-apprenticeship.md
references/worked-examples.md
references/concrete-to-abstract.md
```

The skill and its teaching references are self-contained, with no runtime dependencies, helper scripts, or persistent learning state. References are read selectively and contain teaching material, not user records or full copies of the research papers.
