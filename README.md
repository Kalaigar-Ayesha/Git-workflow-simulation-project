# Git Workflow Simulation Project

This project demonstrates a **real-world Git branching workflow** with feature branches, a development branch, and conflict resolution using Pull Requests (PRs).
It simulates how software teams collaborate and manage code in GitHub.

---

## 🔹 Workflow Overview

* **main** → Production-ready code (stable branch).
* **dev** → Integration branch where new features are merged before going into `main`.
* **feature-\*** → Individual feature branches (e.g., `feature-1`, `feature-2`).

---
### 🔹 Workflow Diagram

         ┌───────────────┐
         │     main      │
         └───────┬───────┘
                 │
            Merge dev
                 │
         ┌───────▼───────┐
         │      dev      │
         └───┬─────┬─────┘
             │     │
     Feature-1   Feature-2
       branch       branch
          │            │
     Pull Request  Pull Request
          │            │
          └─────► Conflict Resolved

---

## 🔹 Steps Implemented

### 1. Setup

* Created a GitHub repository.
* Cloned it locally and initialized `main` and `dev` branches.

### 2. Feature Development

* Created **feature-1** branch → added `feature1.py`.
* Opened a Pull Request (PR) into `dev`.
* Merged PR → `dev` now had `feature-1`.

### 3. Second Feature + Conflict

* Created **feature-2** branch → added `feature2.py`.
* Made a conflicting change in `feature1.py` on both `dev` and `feature-2`.
* Opened PR from `feature-2` → `dev`.
* Resolved merge conflict using GitHub’s conflict editor.
* Merged PR → `dev` now had both `feature-1` and `feature-2`.

### 4. Final Merge

* Merged `dev` → `main` to deliver stable code.

---

## 🔹 Commands Practiced

```bash
# Create & push new branch
git checkout -b feature-1
git push -u origin feature-1

# Stage and commit changes
git add <file>
git commit -m "Message"

# Sync with remote
git pull --rebase origin dev

# Merge into main
git checkout main
git merge dev
git push origin main
```

---

## 🔹 Conflict Resolution Example

During `feature-2` merge, GitHub detected conflicts in `feature1.py`.
Conflict markers looked like this:

```python
print('Hello from Feature 1')
<<<<<<< dev
print('New line from dev')
=======
print('Conflicting change from feature-2')
>>>>>>> feature-2
```

Final resolved file:

```python
print('Hello from Feature 1')
print('New line from dev')
print('Conflicting change from feature-2')
```

---

## 🔹 Key Learnings

✔️ Git basics: `init`, `clone`, `add`, `commit`, `push`, `pull`
✔️ Branching and merging
✔️ Rebasing to keep history clean
✔️ GitHub PRs and collaboration workflow
✔️ Conflict resolution in Pull Requests

---

## 🔹 Repository Structure

```
├── feature1.py   # Added in feature-1
├── feature2.py   # Added in feature-2
└── README.md     # Documentation
```

---

## 🔹 Future Enhancements

* Add a `feature-3` branch with another conflict scenario.
* Demonstrate `git rebase` in practice.
* Show GitFlow with release/hotfix branches.

---
