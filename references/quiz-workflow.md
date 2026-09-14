# Quiz Workflow

Use this workflow when the user asks for a quiz, test, review, or `hint quiz`.

## Select Topics

Honor an explicitly requested topic or scope. Otherwise prioritize:

1. topics with active `weak_points`;
2. `introduced` topics;
3. `practicing` topics;
4. topics never reviewed or reviewed least recently;
5. occasional `understood` topics when useful for retention or transfer.

Avoid repeatedly testing the same wording or narrow fact. If no memory exists, quiz the requested subject without claiming knowledge of prior progress. If neither memory nor a subject is available, ask the user for a subject.

## Ask and Evaluate

- Ask one question at a time and wait for the answer.
- Prefer recall, explanation, comparison, debugging, and application over recognition.
- Do not use multiple choice unless requested or pedagogically necessary.
- Match difficulty to the recorded mastery and the user's demonstrated level.
- Do not reveal the solution before the user answers or gives up.

For `hint quiz`, provide hints progressively. Begin with a directional cue, then a more concrete scaffold, and reveal the answer only when requested. Track hint use as weaker evidence than an unaided answer, without treating it as failure.

Evaluate each answer as `correct`, `partial`, or `incorrect`. Briefly state what was right, correct the important gap, and explain the underlying idea. Be tolerant of equivalent wording and focus on reasoning rather than exact phrasing.

## Update Memory

After each answer, when `.llm-teacher.yml` exists:

- set `last_seen` and `last_reviewed` to the current date;
- update mastery using the rules in `learning-memory.md`;
- add a precise weak point for a material misconception;
- remove or refine a weak point that the answer resolves;
- add at most one concise durable note when it will improve a future quiz.

Do not preserve every answer or build a transcript.

## Finish

Use the number of questions requested by the user; otherwise keep the quiz short. At the end, summarize strengths, remaining weak points, and the best next topic to review. Do not report a numerical grade unless the user asks for one.
