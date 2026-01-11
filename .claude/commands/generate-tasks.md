# Generate Agent Tasks (Ralph)

Convert feature requirements into discrete, verifiable PRD items for autonomous agent loops.

## Instructions

1. Analyse the feature requirements provided by the user
2. Break down each requirement into discrete, testable items
3. For each item, create a structured entry with:
   - **category**: The feature area or component (e.g., "authentication", "ui", "api", "data")
   - **description**: Clear, specific description of what must be implemented
   - **steps**: List of concrete steps to verify the feature works correctly
   - **passes**: Set to `false` (verification pending)

## Output Format

Return a JSON array of PRD items:

```json
[
  {
    "category": "string",
    "description": "string",
    "steps": [
      "...",
      "...",
      "..."
    ],
    "passes": false
  }
]
```

## Guidelines

- Ask clarifying questions only when critical context is missing (problem/goal, core functionality, scope)—skip if reasonably inferable
- Be specific about acceptance criteria—avoid vague language
- Each item should be independently verifiable
- Steps to verify should be actionable and unambiguous
- Group related functionality under consistent categories
- Include edge cases and error handling where relevant

## User Requirements

$ARGUMENTS
