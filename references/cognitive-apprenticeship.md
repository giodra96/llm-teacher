# Cognitive Apprenticeship

## When to Consult

Use when a finished result hides an important decision, or when choosing how much explanation the user needs.

## Source Summary

Collins, Brown, and Holum describe teaching expert strategies through meaningful tasks. Modeling makes the approach observable; coaching and scaffolding support learners as they work; fading reduces support as they become capable. The framework also includes articulation, reflection, and exploration. It discusses applications in reading, writing, and mathematics, rather than evaluating an LLM skill.

## Application to This Skill

- Connect the goal, relevant evidence, chosen action, and check in a short explanation of a consequential decision.
- Explain a prerequisite when the conversation reveals a gap. If the user already applies it correctly, focus on the new difficulty.
- Adjust explanatory detail without withholding the requested result or assigning compulsory practice. This is a limited adaptation of scaffolding, not the full teaching model.

## Original Example

Fictional task: repair a function that rejects zero as a valid quantity.

> The condition `if not quantity` groups zero with missing values. I changed it to `if quantity is None` because the requirement accepts zero and treats only `None` as missing. I checked both inputs: zero now follows the valid path, while `None` still produces the missing-value error. Those checks cover this distinction; they do not establish that every possible input is valid.

For a beginner, explain that Python treats both zero and `None` as false in a condition. If the user has already demonstrated that knowledge, explain only the mismatch between the condition and the requirement. Use this wording only if those changes and checks actually occurred.

## Limits

The full model includes learner participation and feedback. An agent's explanation alone does not reproduce it. Do not infer competence from agreement or silence.

## Source Record

Allan Collins, John Seely Brown, and Ann Holum. 1991. *Cognitive Apprenticeship: Making Thinking Visible*. American Educator, Winter 1991. Relevant sections: “Traditional Apprenticeship” and “From Traditional to Cognitive Apprenticeship.”
