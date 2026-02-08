---
name: learnings-summarizer
description: Extract and summarize learnings from completed tasks. **This skill should ONLY be used when explicitly instructed by the user to extract learnings.** It is not meant to be triggered automatically during task completion.
---

# Learnings Summarizer

This skill provides guidance for extracting and documenting reusable knowledge from completed tasks.

**CRITICAL: This skill focuses on GENERAL, REUSABLE patterns only.**

If the completed work primarily followed existing guidelines without revealing new broadly-applicable insights, DO NOT add learnings. Most implementations should NOT generate new documentation entries.

## When This Skill Activates

This skill is used ONLY when a user explicitly instructs you to extract learnings, summarize insights, or document patterns from completed work. Common triggers include:

- "Extract learnings from this task"
- "Summarize what we learned"
- "Document patterns for future reference"
- "Add to AGENTS.md" (or similar guideline files)
- Explicit requests to capture reusable knowledge

## What to Document

When extracting learnings, focus on information that will help future sessions perform similar tasks more efficiently:

### Include

**General insights about codebase structure or patterns discovered**
- Non-obvious relationships between modules or systems
- Common pitfalls or gotchas encountered and how to avoid them
- Useful commands, build steps, or workflow optimizations
- Clarifications about existing guidelines or conventions
- Architectural patterns that emerged during the work
- Testing strategies that proved effective

**Example of GOOD learning (broadly applicable):**
- ✅ "Test expectations can mask bugs - verify against specification" (general testing insight)

### Exclude

**Task-specific implementation details that only apply to one module/function:**
- Specific algorithm details
- Task-specific constants or magic numbers
- Edge cases unique to a single task
- Implementation choices obvious to readers of that code

**Already documented information:**
- Patterns already covered in existing guidelines
- Standard procedures documented elsewhere

**Temporary or obvious information:**
- Temporary debugging information or workarounds
- Changes that will be obvious to future readers reading the code
- Routine implementation details that don't represent reusable patterns

## Documentation Format

When adding learnings to AGENTS.md or similar files:

1. **Use clear, actionable headings** that describe the domain area
2. **Write in imperative mood** (e.g., "When implementing X...", "For Y...")
3. **Include concrete examples** where helpful
4. **Reference specific code locations** when applicable (use `file:line` format)
5. **Organize by theme** rather than chronological order

### Example Pattern

```markdown
### Domain Name

When working with [specific domain/feature]:

1. **Key pattern description**: Explain what to do and why
2. **Another pattern**: Clear instructions with rationale
3. **Edge case handling**: How to handle specific situations
```

## Extraction Process

When instructed to extract learnings:

1. **Review the completed work** chronologically
2. **Apply the "Different Task" test**: Would this help with a DIFFERENT future implementation?
3. **Identify key insights** that would benefit future work across multiple scenarios
4. **Filter out** task-specific, already-documented, and obvious information
5. **Structure** findings by domain/area
6. **Write clearly** with concrete examples and references
7. **Verify against quality checklist** - especially the red flag checks
8. **Append** to the appropriate section of AGENTS.md or target file

**If no learnings pass the quality checklist, report this to the user** rather than forcing additions.

## Quality Checklist

**Before finalizing learnings, ask: Would this help with a DIFFERENT future task?**

If the answer is "no" or "only if implementing the same task again," do NOT add the learning.

- [ ] Each item provides actionable guidance
- [ ] Information is generic enough to apply to **multiple different scenarios**
- [ ] No task-specific implementation details included (constants, algorithms, specific edge cases)
- [ ] Clear "when to use" context for each guideline
- [ ] References to code locations are specific and helpful
- [ ] Information is not already documented elsewhere
- [ ] **RED FLAG CHECK**: Would this be obvious to someone reading the code? If yes, exclude.
- [ ] **RED FLAG CHECK**: Does this only apply to the specific module just implemented? If yes, exclude.

## Integration

After extracting learnings:

- Append to the most relevant section of AGENTS.md
- If creating a new section, place it logically near related content
- Maintain existing formatting and style consistency
- Ensure no duplication with existing content
