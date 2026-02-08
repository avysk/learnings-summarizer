# learnings-summarizer

A skill for extracting and documenting reusable knowledge from completed tasks.

## Overview

This skill helps capture general, reusable insights from completed work. It's
designed to create documentation that benefits future sessions by documenting
patterns, gotchas, and workflows that apply across multiple scenarios.

This skill is not meant to be triggered automatically during task completion.
It should only be used when explicitly instructed by the user.

## When to Use

Use this skill when you explicitly want to:

- Extract learning from a completed task
- Summarize insights for future reference
- Document patterns that emerged during work
- Add knowledge to `AGENTS.md`

## Key Principles

This skill emphasizes broadly applicable insights:

- Non-obvious relationships between systems
- Common pitfalls and how to avoid them
- Useful commands and workflow optimizations
- Architectural patterns that emerged
- Testing strategies that proved effective

This skill excludes task-specific information:

- Specific algorithms or implementation details
- Constants or magic numbers
- Edge cases unique to a single task
- Information already documented elsewhere
- Changes obvious to future code readers

## How It Works

When activated, the skill:

1. Reviews the completed work chronologically
2. Applies the "Different Task" test: Would this help with a different future
   implementation?
3. Identifies key insights that would benefit future work
4. Filters out task-specific and obvious information
5. Structures findings by domain/area
6. Writes with concrete examples and code references
7. Verifies against quality checklist
