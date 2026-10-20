[README.md](https://github.com/user-attachments/files/33699388/README.md)
# Applied Robotics and AI Project

Course:  Robotics & AI, University of Hertfordshire
Student: LAW LI KANG RAIN (1904VECI)
Lecturer: Sarina Tajudin
Repository: https://github.com/likangliu8-afk/repos1

## 1. Project Overview

This repository holds all deliverables, lab notes, and code for the Applied Robotics and AI
project. It is maintained in parallel with a Trello board that tracks every practical session
and assignment from Week 1 to the present.

## 2. Project Management

- Trello board: (https://trello.com/b/oSrhN1Kk/applied-robotics-ai-project-1904veci)
- Workflow: Backlog → To Do → In Progress → Done
- Every card carries a due date and at least one labels (type + domain)
- Completed cards in Done link to the corresponding Pull Request in this repository

## 3. Git Workflow

### 3.1 Setup

```bash
git clone https://github.com/likangliu8-afk/repos1.git
cd repos1
git status          # confirm you are on main with a clean working tree
```

### 3.2 Everyday Commands

```bash
git status
git add <file>              # stage a file
git commit -m "type: msg"   # commit the staged changes locally
git push origin main        # upload local commits to GitHub
git pull origin main        # fetch and merge remote changes
git branch feature-x        # create a new branch
git checkout feature-x      # switch to that branch
```

Commit message convention (Conventional Commits): use a short prefix —
`feat:`, `fix:`, `docs:`, `test:`, `chore:` — followed by an imperative summary.
Example: `docs: add P2 ROS environment setup notes`.

### 3.3 Add / Commit / Push — What Each Does

These three commands operate on three different layers of the repository:

- **`git add <file>`** moves a change into the **staging area** (the index).
  It decides *which* files will be included in the next commit. You can stage
  one file or many; nothing is written to history at this point. If you stage
  the wrong file you can undo it with `git reset <file>`.

- **`git commit -m "..."`** takes the current staging area and records it as a
  permanent **snapshot** in your **local** repository history. The snapshot
  carries an author, timestamp, message, and a unique hash (e.g. `a3f9c21`).
  After committing, the change is part of *your* local history only — no one
  else can see it yet.

- **`git push origin main`** uploads your local commits to the matching branch
  on the **remote** repository (GitHub). Only after pushing can the lecturer
  or a teammate see or pull your work.

One-line summary:
**add** selects what goes in → **commit** freezes it locally → **push** uploads it.

### 3.4 Branching Strategy

- `main` is always kept in a working, submittable state.
- One feature branch per practical or assignment, named `feature-p<#>`
  (e.g. `feature-p3-pubsub`) or `feature-assignment-<#>`.
- All work happens on the branch. When finished, a **Pull Request (PR)** is
  opened targeting `main`, reviewed, then merged.
- Merged branches are deleted to keep the repository tidy.

Typical cycle:

```bash
git checkout main
git pull origin main
git checkout -b feature-assignment-1
# ... edit, run, test ...
git add .
git commit -m "feat: add assignment 1 deliverables"
git push -u origin feature-assignment-1
# open PR on GitHub, then on main:
git checkout main
git merge feature-assignment-1
git push origin main
git branch -d feature-assignment-1
```

Example: `feature-assignment-1` → PR #1 → merged into `main`.

## 4. Screenshots / Evidence

### 4.1 Trello Board (Full View)

Shows the four-list workflow (Backlog → To Do → In Progress → Done), card labels,
due dates, and completed cards with merged PR indicators.

![Trello board full view](img/trello-board.png)

### 4.2 GitHub Commit History

Shows regular commits on the `main` branch with meaningful messages, including a
merged Pull Request (`Merge pull request #1 from feature/add-project-docs`).

![GitHub commit history](img/github-commits.png)

### 4.3 Trello Card Linked to a GitHub PR

A completed card in the **Done** list ("Document: differences between Add, Commit
and Push") with the `document` label, a due date, and the associated GitHub Pull
Request linked below the description — demonstrating continuous tool usage.

![Trello card with linked PR](img/trello-card-with-pr.png)
