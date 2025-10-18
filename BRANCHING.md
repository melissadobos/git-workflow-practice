# Branching & GitHub Flow — Capstone (FastAPI + PostgreSQL)

## Workflow (simple and strict)
1. **Branch per task**: `feature/<short-desc>` or `fix/<short-desc>`.
2. **Small, topic-focused commits**:
   - Stage by hunk when needed (`git add -p`).
   - Keep each commit about ONE thing.
3. **Open a Pull Request (PR)** to `main`:
   - Fill title + body (what changed, why, any notes).
   - Link the task/issue if applicable.
4. **Review → Merge**:
   - At least **1 approval** required.
   - **Squash & merge** or **merge** (no rebase merge on main).

## Commit messages
- **Subject (≤80 chars)** + blank line + body explaining:
  - What changed, why, anything to watch out for.
- Example:
  - Subject: `Add newsletter page skeleton`
  - Body: “Creates newsletter.md… Reason… Notes…”
- Prefer conventional style when possible:
  - `feat:`, `fix:`, `docs:`, `refactor:`, `test:`, `chore:`

## Merge vs Rebase (rule of thumb)
- **Never rewrite shared history** (`main` or any published team branch).
- It’s OK to **rebase your local feature branch** before opening/while updating a PR to keep history clean.
- If you rebased a branch that was already pushed, use `git push --force-with-lease` (feature branches only).

## Conflict handling
- If a PR is out of date, **merge `main` into the feature branch** (or rebase locally).
- Resolve conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`), test, push.

## Branch protection (main)
- Require **PR reviews** before merging.
- Dismiss stale approvals on new commits.
- Require status checks (when CI is added).
- Disallow direct pushes to `main`.

