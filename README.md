This repository is designed as a hands‑on training kit for practicing common Git workflows.
It contains three exercises:

---

## 1. Merge Conflict Exercise

**Branches involved:** `feature-a`, `feature-b`

- Both branches edit the same lines in `README.md` differently.
- Merging them into `main` will cause a **merge conflict**.
- Practice steps:
  1. Checkout `main`: `git checkout main`
  2. Merge one branch: `git merge feature-a`
  3. Merge the other: `git merge feature-b`
  4. Inspect `README.md` to see conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`).
  5. Resolve the conflict manually and commit the resolution.

---

## 2. Rebase Practice (No Conflicts)

**Branches involved:** `rebase-a`, `rebase-b`

- Each branch adds a different file (`rebase-a.txt` and `rebase-b.txt`).
- Rebasing one branch onto the other will succeed without conflicts.
- Practice steps:
  1. Checkout `rebase-b`: `git checkout rebase-b`
  2. Run: `git rebase rebase-a`
  3. Verify that both files (`rebase-a.txt` and `rebase-b.txt`) exist after the rebase.
  4. Reset if needed: `git rebase --abort` or `git reset --hard`.

---

## 3. Git Bisect Practice (No Code Required)

**Branch involved:** `bisect-practice`

- The branch contains a file `notes.txt` that evolves over several commits.
- One commit introduces a line with `"BUG introduced here"`.
- Practice steps:
  1. Checkout `bisect-practice`: `git checkout bisect-practice`
  2. Start bisect: `git bisect start`
  3. Mark the latest commit as bad: `git bisect bad`
  4. Mark the first commit as good: `git bisect good <commit-hash>`
  5. Git will check out commits between good and bad.
  6. Inspect `notes.txt`:
     - If it contains `"BUG introduced here"`, run `git bisect bad`
     - Otherwise, run `git bisect good`
  7. Continue until Git identifies the exact commit that introduced the bug.
  8. Reset bisect: `git bisect reset`

---
