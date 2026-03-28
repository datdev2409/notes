---
description: Commits all pending changes to GitHub with an auto-generated or user-provided commit message.
---
# Workflow: /commit [optional message]

When the user invokes `/commit` (or `/commit [message]`):

1. **Analyze Changes**: Use `run_command` with `git status` and a brief `git diff` to understand what files have been modified or added in the workspace.
2. **Determine Commit Message**: 
   - If the user provided a `[message]`, use their message.
   - If no message was provided, synthesize a concise semantic commit message based on the analysis from step 1 (e.g., `docs: update service mesh notes` or `chore: sync active learnings`).
3. **Save State**:
// turbo-all
   - Run `git add .`
   - Run `git commit -m "<your determined message>"`
   - Run `git push`
4. **Confirm Success**: Provide a quick confirmation to the user showing the files that were successfully backed up to GitHub.
