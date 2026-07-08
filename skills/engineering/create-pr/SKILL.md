---
name: create-pr
description: >-
  Create a pull request from the current branch with automatically generated title and description
  based on committed changes. Analyzes git history, changed files, and diffs to create comprehensive PR documentation.
compatibility: Requires GitHub CLI (gh) and git
---

# Create Pull Request

Automatically create a pull request with comprehensive documentation based on your committed changes.
You **MUST** consider the user input before proceeding (if not empty).

## Generate PR Title

If user didn't provide a title, generate one from commits and files:

**Title rules**:
- Max 60 characters (GitHub convention)
- Start with context: Image, Curriculum, Video, Units
- Follow with action verb: add, fix, update, refactor, implement
- No period at end

**Examples**:
```
✓ "Image: Add device filtering endpoint"
✓ "Fix scan results parsing bug"
✓ "Curriculum: implement authentication layer"
✓ "Freshdesk: update documentation for v1 release"
✗ "did some work" (too vague)
✗ "Add device filtering endpoint that filters devices by type and subnet (too long)"
```

## Generate PR Description

Create comprehensive PR description with sections:

```markdown
## Summary
<1-3 sentence summary of changes>

## Changes
- Bullet list of key changes
- Extracted from file changes and commits

## Testing
How to test these changes if more than automatic CI tests are needed:
- Step-by-step instructions

## Additional Notes
[Any other context or notes]

<details>
<summary>Original agent plan</summary>

Add this only if the plan exists. 
</details>
```
