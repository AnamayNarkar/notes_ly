# DevOps — Module 2: Version Control and Build Automation
### Study Material | K.J. Somaiya School of Engineering | LY B.Tech Computer Engineering

---

> **IMPORTANT CONTEXT FOR THIS CHAT:**
> All content below is synthesized from the official course slides (`2.1 Git in detail.pdf`, `Introduction to Devops_with Git.pptx`) and cross-referenced against all available PYQs (ESE Nov 2025, ESE with CO-BT, ISE/MSE Re-exam, Sample Question Bank). Sections marked **[GENERATED]** do not appear in official notes/PYQs but are part of the syllabus and have been written as expected exam content.

---

## DELIVERABLE 1 — TOPIC MAP

```
Module 2: Version Control and Build Automation
│
├── 2.1 Introduction to Version Control and Git
│   │
│   ├── Version Control Systems (VCS)
│   │   ├── Need for Source Code Management
│   │   ├── Types of VCS
│   │   │   ├── Local VCS
│   │   │   ├── Centralized VCS (CVCS) — e.g., SVN
│   │   │   └── Distributed VCS (DVCS) — e.g., Git, Mercurial
│   │   └── Benefits of VCS
│   │
│   ├── Introduction to Git
│   │   ├── What is Git (open-source DVCS, GPL license)
│   │   ├── Features of Git
│   │   │   ├── Open Source
│   │   │   ├── Scalable
│   │   │   ├── Distributed
│   │   │   ├── Secure (SHA-1)
│   │   │   ├── Speed (written in C)
│   │   │   ├── Non-linear development support
│   │   │   ├── Branching and Merging
│   │   │   ├── Data Assurance
│   │   │   ├── Staging Area
│   │   │   └── Clean History
│   │   └── Git vs GitHub (distinction)
│   │
│   ├── Git Internals
│   │   ├── Snapshots, Not Differences
│   │   ├── SHA-1 Hash Checksums (Integrity)
│   │   │   ├── 40-character hex string per commit
│   │   │   └── No global version number (vs SVN)
│   │   └── Three Local Areas
│   │       ├── Working Directory
│   │       ├── Staging Area (.index)
│   │       └── Git Repository (.git)
│   │
│   ├── Git File Lifecycle
│   │   └── Untracked → Unmodified → Modified → Staged → (commit) → Unmodified
│   │
│   ├── Git Setup — Local & Remote Repositories
│   │   ├── git config (user.name, user.email, core.editor)
│   │   ├── Local Repository Setup
│   │   │   ├── git init
│   │   │   └── git clone <url>
│   │   ├── Remote Repositories
│   │   │   ├── What is a remote (origin)
│   │   │   ├── git remote add / remove / rename
│   │   │   ├── git push / git pull
│   │   │   └── git fetch
│   │   └── GitHub SSH Setup
│   │       ├── ssh-keygen -t ed25519
│   │       ├── ssh-add
│   │       └── ssh -T git@github.com
│   │
│   ├── Core Git Operations
│   │   ├── git add (stage files)
│   │   ├── git commit -m "message"
│   │   ├── git status / git status -s
│   │   ├── git diff / git diff --cached
│   │   ├── git log / git log --oneline / git log --graph
│   │   └── git reset HEAD -- filename (unstage)
│   │
│   ├── Git Branching
│   │   ├── What is a Branch (lightweight pointer to commit)
│   │   ├── HEAD pointer (points to current branch)
│   │   ├── git branch <name> (create)
│   │   ├── git checkout <branch> (switch)
│   │   ├── git checkout -b <branch> (create + switch)
│   │   ├── git branch -d <branch> (delete)
│   │   ├── git branch (list)
│   │   └── Commit history / divergent history
│   │
│   ├── Git Merging
│   │   ├── Fast-Forward Merge (direct ancestor path)
│   │   ├── Three-Way (Recursive) Merge
│   │   │   └── Uses common ancestor + two branch tips
│   │   └── Merge Commit (has multiple parents)
│   │
│   ├── Git Rebase
│   │   ├── What is rebase (replay commits on top of another branch)
│   │   ├── Rebase vs Merge (clean history vs preserved history)
│   │   └── Golden rule: Never rebase public/shared branches
│   │
│   ├── Git Stash
│   │   ├── git stash (save current work temporarily)
│   │   ├── git stash list
│   │   ├── git stash pop / git stash apply
│   │   └── Use case: urgent hotfix while mid-feature
│   │
│   ├── Merge Conflicts and Resolution
│   │   ├── What causes conflicts
│   │   ├── Identifying conflicted files (git status)
│   │   ├── Conflict markers (<<<<, ====, >>>>)
│   │   └── Resolution steps (edit → add → commit)
│   │
│   ├── History Management
│   │   ├── git log variations
│   │   ├── Git Hooks (pre-commit, post-commit, pre-push)
│   │   └── Branch protection rules
│   │
│   └── Git for DevOps Workflows
│       ├── Git as the source of truth for CI/CD
│       ├── Git-Jenkins integration (triggers on commit)
│       └── Branching strategies for DevOps (feature branches, hotfix, release)
│
└── 2.2 Introduction to Build Tools
    │
    ├── Build Automation Fundamentals
    │   ├── What is Build Automation
    │   └── Why automate builds (eliminate manual errors, repeatability)
    │
    ├── Build and Run Applications — Java
    │   ├── Maven (pom.xml)
    │   │   ├── Build lifecycle: validate → compile → test → package → verify → install → deploy
    │   │   └── Dependency management (Maven Central)
    │   └── Gradle (build.gradle)
    │
    ├── Build and Run Applications — JavaScript
    │   ├── npm / yarn (package.json)
    │   └── npm scripts: install → build → test → start
    │
    ├── Artifact Creation and Publishing
    │   ├── What are Artifacts (JAR, WAR, npm packages, Docker images)
    │   ├── Artifact Versioning (MAJOR.MINOR.PATCH)
    │   └── Publishing to Repository (Nexus, Maven Central, npm registry)
    │
    └── Integration of Build Tools with Docker
        ├── Build Tool → Artifact → Dockerfile → Docker Image
        └── Multi-stage Docker builds [GENERATED]
```

---

## DELIVERABLE 2 — TOPIC-WISE ASKED QUESTION TYPES

**Legend:**  `[P]` = Appeared in official PYQ  |  `[S]` = Appeared in Sample/Question Bank  |  `-` = Not yet asked but expected from syllabus

| # | Topic | Short Note (2-5M) | Long Answer (10M) | Diagram | Command/Applied | Scenario-Based | PYQ Status |
|---|---|:---:|:---:|:---:|:---:|:---:|---|
| 1 | VCS types (Local / CVCS / DVCS) | Yes | Yes | Yes | - | - | **[P]** ESE |
| 2 | Benefits of Git / VCS | Yes | Yes | - | - | - | **[P]** ESE, ISE |
| 3 | Source Code Management Architecture | - | Yes | Yes | - | - | **[P]** ESE |
| 4 | Git Internals (Snapshots, SHA-1) | Yes | Yes | Yes | - | - | **[S]** |
| 5 | Three Areas: Working Dir / Staging / Repo | Yes | Yes | Yes | - | - | **[S]** |
| 6 | Git File Lifecycle | Yes | Yes | Yes (diagram) | - | - | **[S]** |
| 7 | Git Setup (config, init, clone) | Yes | - | - | Yes | Yes | **[S]** |
| 8 | Core Git Commands (add, commit, status, diff, log) | Yes | Yes | - | Yes | Yes | **[P]** ESE (commit history Q) |
| 9 | Git Branching (create, switch, HEAD) | Yes | Yes | Yes (diagram) | Yes | Yes | **[P]** ESE |
| 10 | Git Merging (fast-forward, 3-way) | Yes | Yes | Yes (diagram) | Yes | Yes | **[P]** ESE |
| 11 | Git Rebase (vs Merge) | Yes | Yes | - | Yes | Yes | **[S]** |
| 12 | Git Stash | Yes | Yes | - | Yes | Yes | **[S]** |
| 13 | Merge Conflicts and Resolution | Yes | Yes | - | Yes | Yes | **[P]** ESE, Sample |
| 14 | History Management (git log, hooks, branch protection) | Yes | Yes | - | Yes | Yes | **[P]** ESE |
| 15 | Remote Repos (origin, push, pull, remote add) | Yes | Yes | - | Yes | Yes | **[S]** |
| 16 | SSH Setup for GitHub | Yes | - | - | Yes | - | - |
| 17 | Git for DevOps / CI integration | Yes | Yes | - | - | Yes | **[P]** ISE, ESE |
| 18 | Build Automation Fundamentals | Yes | Yes | - | - | Yes | **[S]** |
| 19 | Java Build Lifecycle (Maven/Gradle) | Yes | Yes | - | Yes | Yes | **[S]** |
| 20 | JS Build (npm) | Yes | - | - | Yes | - | **[S]** |
| 21 | Artifacts (JAR, WAR, npm packages) | Yes | Yes | - | - | Yes | **[S]** |
| 22 | Artifact Publishing / Repository | Yes | Yes | - | - | Yes | **[S]** |
| 23 | Build Tools + Docker Integration | Yes | Yes | - | - | Yes | **[S]** |

---

## DELIVERABLE 3 — TOPIC-BY-TOPIC DETAILED BREAKDOWN

---

### TOPIC 1: Version Control Systems (VCS)

#### What it is and why it matters

A **Version Control System** tracks changes to files over time, lets you go back to any earlier version, and allows multiple developers to collaborate without overwriting each other's work.

Without VCS, you end up with folders named `project_final`, `project_final_v2`, `project_ACTUAL_final` — which is a disaster for teams.

#### Types of VCS — the evolution

**1. Local VCS**

The simplest approach. A local database on your machine stores all versions. Only you can access it. If your machine fails, everything is lost. If you accidentally write to the wrong file, there is no safety net.

```
  Local Computer
  ┌──────────────────┐
  │  Version DB      │
  │  [Version 3] ──► File (current)
  │  [Version 2]
  │  [Version 1]
  └──────────────────┘
```

**2. Centralized VCS (CVCS) — e.g., SVN, CVS, Perforce**

A single central server holds all versioned files. Developers "check out" files from the center. Better for teams because everyone can see what others are doing. But there is a **single point of failure** — if the server goes down, no one can commit or collaborate. Every commit increments a global version number.

```
  Central VCS Server         Computer A
  ┌────────────────┐         ┌──────────┐
  │  [Version 3]  ├─────────► Checkout ► File
  │  [Version 2]  │         └──────────┘
  │  [Version 1]  ├─────────► Computer B
  └────────────────┘           File
```

**3. Distributed VCS (DVCS) — e.g., Git, Mercurial, Bazaar**

Every developer has a **full mirror** of the entire repository including all history. You can commit locally without internet. Even if the central server dies, any client's copy can restore it. "Every checkout is a full backup."

```
  Server Computer            Computer A (Full Clone)
  ┌────────────────┐         ┌──────────────────────┐
  │  [Version DB]  │◄───────►│  File + Version DB   │
  └────────────────┘         └──────────────────────┘
         ▲                          ▲
         │                          │
  Computer B (Full Clone)    (works offline, commits locally)
  ┌──────────────────────┐
  │  File + Version DB   │
  └──────────────────────┘
```

Git uses SHA-1 hashes (40-character hex strings) instead of sequential version numbers, since multiple users commit independently and there is no global counter.

#### Benefits of VCS

- **Complete change history**: Every change is recorded with who, when, and why.
- **Simultaneous collaboration**: Multiple developers can work in parallel.
- **Branching and merging**: Parallel lines of development.
- **Traceability**: Link every change to a bug ticket or feature.
- **Backups**: The repository IS the backup.

#### How to answer in exam

- Short note (5M): Define VCS, name 3 types, briefly describe each, give one benefit each. Draw a diagram of CVCS vs DVCS.
- Long answer (10M): Full explanation with diagrams of all 3 types + comparison table + benefits.

---

### TOPIC 2: Introduction to Git

#### What is Git

Git is an **open-source, distributed version control system** released under the **GPL (General Public License)**. It was originally developed by **Linus Torvalds** in 2005 to manage the Linux kernel source code. It is designed to handle everything from small to very large projects with speed and efficiency.

Key superiority over other SCMs: Git is faster, safer, supports offline work, and its branching model is far superior to tools like SVN, CVS, Perforce, and ClearCase.

#### Features of Git (remember these — direct exam question)

| Feature | Explanation |
|---|---|
| Open Source | Released under GPL; free to use and modify |
| Scalable | Handles growth in users and codebase without performance degradation |
| Distributed | Every clone is a full repository; no single point of failure |
| Security | Uses SHA-1 hashing; tampering is detectable |
| Speed | Core written in C; most ops are local (no network required) |
| Non-linear development | Supports parallel branches and feature tracks |
| Branching and Merging | Create/delete/merge branches in seconds |
| Data Assurance | Checksums ensure data integrity during transit and storage |
| Staging Area | Preview commits before finalizing; stage selectively |
| Clean History | Maintain a readable, purposeful commit log |

#### What is GitHub (distinct from Git)

GitHub is a **web-based hosting service for Git repositories**. Git is the tool; GitHub is the platform. You can use Git completely locally or on any server — GitHub is simply a popular remote host.

GitHub additionally provides: Bug tracking, Pull requests, Project management, Code review, CI/CD via GitHub Actions, Team management.

#### Benefits of Git

- **Save Time**: Operations like branching take milliseconds.
- **Offline Working**: Commit, branch, and view history without internet.
- **Undo Mistakes**: Roll back to any previous state.
- **Track Changes**: Complete audit trail with author and timestamp.
- **Collaborate**: Multiple developers can work on the same codebase safely.

#### How to answer in exam

- Short note (5M): Define Git as open-source DVCS, list 5-6 features with one-line explanation each, distinguish from GitHub.
- Diagram: Draw the distributed network diagram (users with local repos all connected to origin).

---

### TOPIC 3: Git Internals

#### Snapshots, Not Differences

Most VCSs (like SVN) store data as a **list of file-based changes (deltas)**. For each version, they store only what changed.

```
  SVN approach (delta-based):
  Version 1 → Version 2 → Version 3 → Version 4 → Version 5
  file A: [A] ──────────► [Δ1] ──────────────────► [Δ2]
  file B: [B] ────────────────────────────────────► [Δ1]
  file C: [C] ──────────► [Δ1] ──────────────────► [Δ2]
```

Git instead stores **snapshots** of the entire project at each commit. If a file has not changed, it stores a link (pointer) to the previous identical version — not a duplicate.

```
  Git approach (snapshot-based):
  Version 1 → Version 2 → Version 3 → Version 4 → Version 5
  file A: [A]  [A1]  [A1]  [A2]  [A2]
  file B: [B]  [B]   [B]   [B1]  [B2]
  file C: [C]  [C1]  [C2]  [C2]  [C3]
  (dashed boxes = pointer to unchanged previous version)
```

This is a fundamental architectural difference that enables Git's speed for branching and history traversal.

#### SHA-1 Checksums — Git Has Integrity

Every commit in Git is identified by a **40-character hexadecimal SHA-1 hash** (e.g., `1677b2d5e3a8f9...`). This hash is computed from:
- The contents of files in the commit
- The timestamp
- The author information
- The parent commit hash(es)

Because of this, it is **cryptographically impossible** to change any historical commit without changing all subsequent hashes — Git detects tampering.

SVN used a global incrementing number (r1, r2, r3...). This does not work in a distributed system where multiple users commit independently. Git's SHA-1 approach solves this.

In `git log --oneline`:
```
1677b2d  Edited first line of readme
258efa7  Added line to readme
0e52da7  Initial commit
```

Only first 7 characters are shown in most displays, but the full 40-char hash is stored.

#### Three Local Areas of a Git Project

```
  Working Directory     Staging Area (.index)     Git Repository (.git)
  ┌──────────────┐      ┌──────────────────┐      ┌──────────────────┐
  │  Unmodified/ │─git  │                  │─git  │                  │
  │  Modified    │─add─►│  Staged Files    │─comm─►  Committed Files │
  │  Files       │      │                  │ -it  │                  │
  └──────────────┘      └──────────────────┘      └──────────────────┘
        ▲                                                    │
        └────────────────── git checkout ───────────────────┘
```

- **Working Directory**: Where you edit files. Files here are either tracked (unmodified/modified) or untracked (new files Git doesn't know about yet).
- **Staging Area** (also called Index): An intermediate zone. When you `git add`, a snapshot of the file is placed here. It acts as a "preview" of your next commit. You can selectively stage only some changes.
- **Git Repository** (.git directory): The permanent database of all commits, branches, and history. When you `git commit`, the staged snapshot moves here permanently.

**File states summary:**
- File in .git directory → **Committed**
- File modified and added to staging → **Staged**
- File changed but not staged → **Modified**
- New file Git has never seen → **Untracked**

#### Git File Lifecycle Diagram

```
  ┌──────────┐  add file   ┌────────────┐  edit file  ┌──────────┐  stage file  ┌────────┐
  │Untracked │────────────►│Unmodified  │────────────►│ Modified │─────────────►│ Staged │
  └──────────┘             └────────────┘             └──────────┘              └────────┘
                                 ▲                                                    │
                                 │                     commit                         │
                                 └────────────────────────────────────────────────────┘
  (remove file → back to Untracked from Unmodified)
```

#### How to answer in exam

- Diagram of the 3 areas is very commonly asked — always draw it.
- For "Snapshots vs Differences" — draw both diagrams side by side.
- SHA-1 discussion: explain why no global version number works in DVCS.

---

### TOPIC 4: Git Setup — Local and Remote Repositories

#### Setting up Git (First-Time Configuration)

```bash
# Set identity (recorded in every commit)
$ git config --global user.name "Your Name"
$ git config --global user.email "your@email.com"

# Set preferred editor (vim is default)
$ git config --global core.editor emacs

# Verify settings
$ git config --list
```

The `--global` flag applies these settings to all repos on your system. Omit it for project-specific settings.

#### Creating a Local Repository

**Scenario A: Start from scratch**
```bash
$ mkdir myproject && cd myproject
$ git init                     # Creates .git/ directory
$ git add file1.java           # Stage files
$ git commit -m "Initial commit"
```

**Scenario B: Clone an existing repository**
```bash
$ git clone https://github.com/user/repo.git
$ git clone https://github.com/user/repo.git  local-folder-name
```
Cloning gives you: the full history of the project, the working files, and a `.git/` directory. It also automatically sets up `origin` as the remote alias.

#### Remote Repositories

A remote is a version of your project hosted on the internet or a network.

```bash
# View configured remotes
$ git remote         # shows short names
$ git remote -v      # shows URLs (fetch and push)

# Add a remote
$ git remote add origin https://github.com/user/repo.git

# Rename a remote
$ git remote rename origin newname

# Remove a remote
$ git remote remove origin

# Pull = fetch + merge (gets latest from remote into local branch)
$ git pull origin master

# Push = send local commits to remote
$ git push origin master
```

`origin` is just a conventional alias for the remote URL. When you clone a repo, Git sets this automatically. You can name it anything.

#### Good Practice for Collaboration

1. Add and commit your changes locally.
2. Pull from remote (to get any changes teammates pushed; resolve conflicts if any).
3. Push your changes to remote.

#### SSH Key Setup for GitHub

GitHub supports two connection methods: HTTPS and SSH. SSH keys allow you to authenticate without typing username/password every push.

```bash
# 1. Generate key pair
$ ssh-keygen -t ed25519 -C "your@email.com"

# 2. Start ssh-agent
$ eval `ssh-agent -s`

# 3. Add key to agent
$ ssh-add ~/.ssh/id_ed25519

# 4. Copy the PUBLIC key (~/.ssh/id_ed25519.pub) and add it in
#    GitHub Settings → SSH and GPG keys

# 5. Test connection
$ ssh -T git@github.com
# Hi username! You've successfully authenticated...
```

After this, use SSH URLs (`git@github.com:user/repo.git`) instead of HTTPS URLs.

#### Two Workflows to Get Code on GitHub

**Option 1 — Existing local repo:**
1. Create new repo on GitHub.
2. `git remote add origin <url>`
3. `git push origin master`

**Option 2 — Start fresh from GitHub:**
1. Create new repo on GitHub.
2. `git clone <url>`
3. Do work locally.
4. `git push origin master`

#### How to answer in exam

- Commands-based questions: Write the exact commands with brief explanation.
- Scenario (team of 5 sharing a Java app): Explain Git setup steps, local vs remote concept.

---

### TOPIC 5: Core Git Operations

#### Basic Workflow

```
  1. Modify files in working directory
  2. git add <files>          → moves snapshot to staging area
  3. git commit -m "message"  → permanently records staged snapshot in .git/
```

#### Key Commands Reference

```bash
# Stage specific files
$ git add README.txt hello.java

# Stage all changes in current directory
$ git add .

# Commit with inline message
$ git commit -m "Fixing bug #22"

# Stage all tracked modified files AND commit in one step
$ git commit -a -m "Make a change"

# Check current status (verbose)
$ git status

# Check current status (short)
$ git status -s
# M = modified, A = added, ?? = untracked
# First column = staging area, Second column = working tree

# See unstaged changes (what's changed but not yet added)
$ git diff

# See staged changes (what will go into the next commit)
$ git diff --cached      # or: git diff --staged

# View commit history
$ git log
$ git log --oneline      # compact one-line per commit
$ git log --oneline --graph  # ASCII graph of branches

# Unstage a file (undo git add)
$ git reset HEAD -- filename

# Discard working directory changes for a file
$ git checkout -- filename

# See all configured remotes
$ git remote -v

# Clone a repo
$ git clone <url>
```

#### Status and Diff — Understanding the Output

After editing a file but before staging:
- `git status` shows: "Changes not staged for commit: modified: rea.txt"
- `git diff` shows: the actual line-by-line diff (what changed but not staged)
- `git diff --cached` shows: nothing (nothing is staged yet)

After `git add rea.txt`:
- `git status` shows: "Changes to be committed: modified: rea.txt"
- `git diff` shows: nothing (working tree matches staging)
- `git diff --cached` shows: the actual staged changes

---

### TOPIC 6: Git Branching

#### What is a Branch

A **branch** in Git is simply a **lightweight, movable pointer** to a specific commit. When you create a new branch, Git just creates a new pointer — it does NOT copy the entire project directory (unlike older VCSs where branching meant copying files, taking minutes). In Git, branching is instantaneous.

The **default branch** is `master` (or `main` in modern convention). It is not special in any way — it is just the name `git init` gives the first branch.

**HEAD** is a special pointer that always points to the branch you currently have checked out. It moves forward automatically with each commit.

#### Git Data Storage (Internal Structure of a Commit)

When you run `git add README test.rb LICENSE` and `git commit`:

Git stores:
- **3 blobs**: one per file (file contents)
- **1 tree object**: maps filenames to blobs
- **1 commit object**: points to the tree + stores metadata (author, message, timestamp, parent commit pointer)

```
  Commit Object (98ca9)      Tree Object (92ec2)       Blobs
  ┌─────────────────┐        ┌─────────────────┐       ┌──────────┐
  │ tree  92ec2     │───────►│ blob 5b1d3 README│──────►│ README   │
  │ author Scott    │        │ blob 911e7 LICENSE│──────►│ LICENSE  │
  │ committer Scott │        │ blob cba0a test.rb│─────►│ test.rb  │
  │ "Initial commit"│        └─────────────────┘       └──────────┘
  └─────────────────┘
```

Each subsequent commit has a `parent` field pointing to the previous commit, forming a chain.

#### A Branch and Its Commit History

```
  HEAD
   │
   ▼
  master
   │
   ▼
  f30ab ◄──── 34ac2 ◄──── 98ca9
   │            │            │
  [Snapshot C] [Snapshot B] [Snapshot A]
```

When you create a new branch `testing`:
```bash
$ git branch testing
```

```
  HEAD
   │
   ▼
  master         testing
   │              │
   └──────┬───────┘
          ▼
         f30ab ◄──── 34ac2 ◄──── 98ca9
```

`git branch` only CREATES the pointer. HEAD still points to `master`. To actually switch:

```bash
$ git checkout testing
```

Now HEAD points to `testing`. The next commit will advance `testing`, while `master` stays at `f30ab`.

#### Creating, Listing, Switching, Deleting Branches

```bash
# Create a branch
$ git branch experimental

# List all branches (* = current branch)
$ git branch

# Switch to a branch
$ git checkout experimental

# Create AND switch in one step (most common workflow)
$ git checkout -b iss53

# Delete a branch (after merging)
$ git branch -d hotfix

# View branch history as a graph
$ git log --graph --oneline
```

#### Real-World Branching Workflow Example

You are working on `master`. Issue #53 arrives. You create a feature branch. Midway, a production hotfix is needed urgently.

```bash
# Start working on issue 53
$ git checkout -b iss53
$ vim index.html
$ git commit -a -m "Create new footer [issue 53]"

# Urgent hotfix arrives — stash or commit, then:
$ git checkout master          # go back to stable master
$ git checkout -b hotfix       # create hotfix branch
$ vim index.html
$ git commit -a -m "Fix broken email address"

# After testing, merge hotfix into master
$ git checkout master
$ git merge hotfix             # Fast-forward merge
# Delete hotfix branch
$ git branch -d hotfix

# Go back to issue 53 work
$ git checkout iss53
$ vim index.html
$ git commit -a -m "Finish the new footer [issue 53]"

# Eventually merge iss53 into master
$ git checkout master
$ git merge iss53              # Three-way merge (with merge commit)
$ git branch -d iss53
```

State during hotfix (divergent branches):
```
  HEAD → master
  master → C4 (hotfix)
  iss53  → C3

  C0 ← C1 ← C2 ← C4  ← master
              ▲
              └── C3 ← iss53
```

#### How to answer in exam

- Always draw the branch diagram showing HEAD, branch pointers, and commit nodes.
- For "why is Git branching better": it is instantaneous (just a pointer), no file copying.
- For "HEAD" — explain it as the special pointer that tells Git which branch/commit you are currently working on.

---

### TOPIC 7: Git Merging

#### Fast-Forward Merge

Happens when the branch being merged into is a **direct ancestor** of the branch being merged in. There is no divergent history, so Git simply moves the pointer forward — no new commit is created.

```
BEFORE:                        AFTER (fast-forward):
master → C2                    master → C4 (= hotfix)
hotfix → C4                    hotfix → C4
C0 ← C1 ← C2 ← C4            C0 ← C1 ← C2 ← C4
```

```bash
$ git checkout master
$ git merge hotfix
# Output: "Fast-forward"
```

No merge commit. Master pointer just jumps forward to C4.

#### Three-Way (Recursive) Merge

Happens when the two branches have **diverged** — neither is a direct ancestor of the other. Git must identify the common ancestor, then combine changes from both tips.

```
         master
           │
           ▼
C0 ← C1 ← C2 ← C4     ← master (Snapshot to Merge Into)
            │
            └── C3 ← C5 ← iss53 (Snapshot to Merge In)

Common Ancestor: C2
```

Git creates a **new merge commit (C6)** that has TWO parents (C4 and C5):

```bash
$ git checkout master
$ git merge iss53
# Output: "Merge made by the 'recursive' strategy."
```

```
C0 ← C1 ← C2 ← C4 ← C6 ← master (C6 is merge commit, has 2 parents)
                 ▲          
            C3 ← C5 ← iss53
```

The merge commit C6 is special — it preserves the fact that two independent lines of development were merged.

#### How to answer in exam

- Draw before/after diagrams for both merge types.
- Key distinction: Fast-forward = no new commit, pointer moves. Three-way = new merge commit with 2 parents.

---

### TOPIC 8: Git Rebase

#### What is Rebase

Rebase **replays** commits from one branch on top of another, creating a linear history. Unlike merge (which preserves the branch structure), rebase rewrites history.

**Scenario:** `iss53` branched from `master` at C2. Both have diverged.

```
BEFORE REBASE:
C0 ← C1 ← C2 ← C4  ← master
             ▲
             └── C3 ← iss53
```

```bash
$ git checkout iss53
$ git rebase master
```

```
AFTER REBASE:
C0 ← C1 ← C2 ← C4 ← C3'  ← iss53
              ▲
             master
```

C3' is a new commit with the same changes as C3 but a different parent (C4 instead of C2). The history looks as if iss53 was always developed linearly after master.

Then to bring master forward:
```bash
$ git checkout master
$ git merge iss53       # This is now a fast-forward
```

#### Rebase vs Merge — When to Use Which

| Aspect | Merge | Rebase |
|---|---|---|
| History | Preserves branch structure (merge commits visible) | Creates clean linear history |
| Merge commit | Yes (two parents) | No (rewrites commits) |
| Traceability | Easy to see when branches diverged | Harder to trace original branch point |
| Use when | Merging feature into main (want to preserve history) | Cleaning up local feature branch before PR |
| Safety | Safe on public/shared branches | **NEVER rebase public branches** |

**Golden rule**: Rebase is for local cleanup. Once commits are pushed and others are working on them, rebasing rewrites history and causes major conflicts for teammates.

#### How to answer in exam

- Scenario Q: "A PM wants a clean history with no unnecessary merge commits" → Use rebase on feature branches before merging.
- Risk: If you rebase a branch that others have already pulled, their history diverges and merging becomes a nightmare.

---

### TOPIC 9: Git Stash

#### What is Git Stash

Stash temporarily saves your **uncommitted changes** (both staged and unstaged) and reverts the working directory to a clean state. Use it when you need to switch context urgently (e.g., handle a hotfix) but your current feature is incomplete and not ready to commit.

#### The Problem Without Stash

You are halfway through a feature. Boss calls — production is down. If you switch branches without committing, Git might not let you, or your unfinished changes bleed into the hotfix branch.

#### Stash Workflow

```bash
# Save current work to stash (clean working dir)
$ git stash

# Or with a descriptive message
$ git stash push -m "WIP: payment feature"

# List all stashes
$ git stash list
# stash@{0}: On feature: WIP: payment feature
# stash@{1}: On feature: half-done login

# Now switch to master, create hotfix branch, fix issue, merge, push

# Come back and restore your work
$ git stash pop         # applies most recent stash and removes it from stash list

# Or apply without removing from list
$ git stash apply stash@{0}

# Remove a specific stash
$ git stash drop stash@{0}

# Show what's in the stash
$ git stash show
```

#### Stash vs Commit

| | `git stash` | `git commit` |
|---|---|---|
| Saves to | Temporary stash stack | Permanent repository history |
| Appears in `git log` | No | Yes |
| Shareable with team | No | Yes (after push) |
| Use case | Incomplete work, context switching | Completed, meaningful unit of work |

#### How to answer in exam

- Scenario: Developer mid-feature, urgent hotfix needed → `git stash` → fix hotfix → `git stash pop`.
- Commands must be in order: stash → checkout master → checkout -b hotfix → fix → commit → merge → checkout feature → stash pop.

---

### TOPIC 10: Merge Conflicts and Resolution

#### What Causes a Merge Conflict

A **merge conflict** occurs when:
- Two developers modify the **same lines** in the same file in different branches, OR
- One developer deletes a file that another developer modified.

Git cannot automatically decide which version is correct, so it asks you to resolve it manually.

#### Identifying Conflicts

```bash
$ git merge iss53
# CONFLICT (content): Merge conflict in index.html
# Automatic merge failed; fix conflicts and then commit the result.

$ git status
# Both modified: index.html
```

#### Conflict Markers in the File

Git marks the conflicted file like this:

```
<<<<<<< HEAD
<div>Contact us at: webmaster@example.com</div>
=======
<div>Contact us at: support@example.com</div>
>>>>>>> iss53
```

- Everything between `<<<<<<< HEAD` and `=======` is what YOUR current branch (master) had.
- Everything between `=======` and `>>>>>>> iss53` is what the incoming branch (iss53) had.

#### Step-by-Step Conflict Resolution

```
Step 1: Run `git status` to find all conflicted files.

Step 2: Open each conflicted file in an editor.
        Remove the conflict markers and keep/combine the content you want:
        <div>Contact us at: support@example.com</div>

Step 3: Stage the resolved file:
        $ git add index.html

Step 4: Verify all conflicts are resolved:
        $ git status

Step 5: Complete the merge with a commit:
        $ git commit -m "Merge iss53 into master - resolved contact email conflict"
```

#### Prevention Using Git Hooks and Branch Protection

**Git Hooks**: Scripts that run automatically at key Git events.

| Hook | Trigger | Use in DevOps |
|---|---|---|
| `pre-commit` | Before `git commit` runs | Run linters, unit tests |
| `commit-msg` | After commit message is typed | Enforce message format |
| `pre-push` | Before `git push` runs | Run full test suite |
| `post-receive` | Server-side, after push received | Trigger CI/CD pipeline |

Hooks are stored in `.git/hooks/`. They are shell scripts named after the hook event.

**Branch Protection Rules** (on GitHub/GitLab):
- Require pull request reviews before merging
- Require status checks (CI must pass) before merging
- Disallow direct pushes to `main`/`master`
- Require signed commits

These prevent poorly tested or incomplete code from reaching production branches.

#### How to answer in exam

- "What causes conflict" — same lines modified in both branches.
- Draw the conflict marker structure clearly.
- Always list all steps (status → edit → add → commit) in sequence.
- For Jenkins+Git Q (ESE): hooks trigger Jenkins pipeline automatically; branch protection ensures CI must pass before merge.

---

### TOPIC 11: History Management

#### git log — Viewing History

```bash
$ git log                       # full history with author, date, message
$ git log --oneline             # compact, one line per commit
$ git log --oneline --graph     # visual branch graph in terminal
$ git log -5                    # show only last 5 commits
$ git log --author="Anamay"     # filter by author
$ git log --since="2025-01-01"  # filter by date
$ git log -- filename           # history of a specific file
```

Sample output of `git log --oneline`:
```
f30ab6c  Add feature X
34ac2e7  Fix bug #45
98ca9b2  Initial commit
```

#### Git for DevOps — How Git Powers CI/CD

In a DevOps pipeline, every push to the repository is an event that triggers automated processes:

```
Developer → git push → Remote Repository (GitHub/GitLab)
                              │
                              ▼ (webhook trigger)
                         Jenkins / CI Server
                              │
                 ┌────────────┼────────────┐
                 ▼            ▼            ▼
              Build         Test         Deploy
          (mvn package)  (JUnit/Jest)  (Docker/K8s)
```

Git provides:
- **Single source of truth**: All code lives in one place; all versions tracked.
- **Trigger mechanism**: Every commit/push can trigger a CI/CD pipeline.
- **Rollback capability**: If a deployment fails, `git revert` or `git reset` brings you back instantly.
- **Branch isolation**: Feature branches allow dev/test/staging environments to mirror specific branches.

**Git Branching Strategies for DevOps:**

| Strategy | Structure | Best For |
|---|---|---|
| Feature Branch | `main` + `feature/*` | Small teams, frequent merges |
| Git Flow | `main`, `develop`, `feature/*`, `release/*`, `hotfix/*` | Larger projects with release cycles |
| Trunk-Based | Single `main` branch, short-lived feature branches | High-frequency CI/CD teams |

#### How to answer in exam

- "How does Git support CI in DevOps?" — Events (push/PR) trigger webhooks → Jenkins → automated build/test/deploy.
- "Jenkins pipeline failed from Git commit" (ESE Q3iii) — Git hooks (pre-push to run tests), branch protection (require CI pass before merge into main), Jenkins integration (SCM polling or webhooks).

---

### TOPIC 12: Build Automation Fundamentals

> **[GENERATED]** — Build automation specifics (Maven/Gradle/npm) are not covered in the provided PDF slides. This content is written from syllabus expectations and common exam patterns. Marked accordingly.

#### What is Build Automation [GENERATED]

Build automation is the process of **scripting the steps** required to compile, test, package, and deploy software — eliminating the need to run these steps manually before every release.

Without automation, a developer must:
1. Manually compile source files.
2. Manually download and link dependencies.
3. Manually run tests.
4. Manually create JAR/WAR files.
5. Manually copy files to the server.

This is error-prone, slow, and not repeatable. Build automation tools handle all of this with a single command.

#### Why Build Automation Matters in DevOps [GENERATED]

- **Repeatability**: The same build process every time, on every machine.
- **Speed**: CI pipelines can run in minutes, not hours.
- **Early defect detection**: Tests run on every build.
- **Traceability**: Build logs capture exactly what was run.

---

### TOPIC 13: Build and Run Applications — Java [GENERATED]

#### Maven

Maven uses a `pom.xml` (Project Object Model) file to describe the project structure, dependencies, and build steps.

**Standard Maven Build Lifecycle:**

```
validate → initialize → compile → test → package → verify → install → deploy
```

| Phase | What happens |
|---|---|
| `validate` | Checks that the project structure is correct |
| `compile` | Compiles Java source code into `.class` files |
| `test` | Runs unit tests (JUnit); build fails if tests fail |
| `package` | Packages compiled code into JAR or WAR file |
| `verify` | Runs integration tests |
| `install` | Copies artifact to local Maven repository (`~/.m2/`) |
| `deploy` | Uploads artifact to remote repository (Nexus, Maven Central) |

**Common Maven Commands:**

```bash
mvn compile        # compile source
mvn test           # compile + run tests
mvn package        # compile + test + create JAR/WAR
mvn clean package  # clean previous build, then package
mvn install        # package + install to local repo
```

**Dependency Management:** Maven downloads dependencies from Maven Central (or Nexus proxy) and caches them in `~/.m2/repository/`. You just declare what you need in `pom.xml` and Maven fetches the rest.

```xml
<dependencies>
  <dependency>
    <groupId>org.springframework</groupId>
    <artifactId>spring-core</artifactId>
    <version>5.3.0</version>
  </dependency>
</dependencies>
```

#### Gradle [GENERATED]

An alternative to Maven using a `build.gradle` (Groovy or Kotlin DSL) file. More flexible and faster than Maven due to incremental builds and build caching.

```bash
./gradlew build    # compile + test + package
./gradlew test     # run tests only
./gradlew jar      # create JAR
```

---

### TOPIC 14: Build and Run Applications — JavaScript [GENERATED]

JavaScript/Node.js projects use **npm** (Node Package Manager) or **yarn**.

The `package.json` file is the equivalent of Maven's `pom.xml`:

```json
{
  "name": "my-app",
  "version": "1.0.0",
  "scripts": {
    "build": "webpack --mode production",
    "test": "jest",
    "start": "node server.js"
  },
  "dependencies": {
    "express": "^4.18.0"
  }
}
```

**Common npm commands:**

```bash
npm install         # download all dependencies (reads package.json)
npm run build       # build the application
npm test            # run tests
npm start           # start the application
npm publish         # publish package to npm registry
```

---

### TOPIC 15: Artifact Creation and Publishing

> **[GENERATED]** — Specific artifact repository tools like Nexus are covered in Module 3. This section covers artifact concepts as they relate to Module 2 (build output).

#### What is an Artifact [GENERATED]

An **artifact** is the output of a build process — the deployable unit of software.

| Language | Artifact Type | Extension |
|---|---|---|
| Java (library) | JAR (Java Archive) | `.jar` |
| Java (web app) | WAR (Web Archive) | `.war` |
| Java (enterprise) | EAR (Enterprise Archive) | `.ear` |
| JavaScript (npm) | npm package | published to registry |
| Docker | Docker Image | stored in registry |

#### Why Store Artifacts in a Repository [GENERATED]

Without a proper artifact repository:
- Developers share JAR files via email or Slack — different teams may use different versions.
- No versioning — impossible to reproduce builds from 6 months ago.
- No access control — anyone can overwrite artifacts.
- Deployment teams cannot pull the artifact reliably.

With a repository (Nexus, Artifactory, Maven Central):
- Single source of truth for all build outputs.
- Versioned: every release is stored with its exact dependencies.
- Reproducible: any team can pull the exact artifact used in production.
- Auditable: who pushed what, when.

#### Artifact Versioning [GENERATED]

Use Semantic Versioning: `MAJOR.MINOR.PATCH` (e.g., `1.4.2`)

```
1.4.2
│ │ └── PATCH: bug fixes, no API changes
│ └──── MINOR: new features, backward compatible
└────── MAJOR: breaking API changes
```

Artifacts are typically named like: `myapp-1.4.2.jar`

---

### TOPIC 16: Integration of Build Tools with Docker

> **[GENERATED]** — This topic is from the syllabus but not explicitly in the provided notes. Written from expected exam perspective.

#### The Full Pipeline [GENERATED]

```
Source Code (Git)
      │
      ▼ (git push → Jenkins triggered)
Build Tool (Maven/npm)
      │ mvn package / npm run build
      ▼
Artifact (app.jar / bundle.js)
      │
      ▼ (Dockerfile reads the artifact)
Docker Image (docker build)
      │
      ▼ (docker push)
Docker Registry (Docker Hub / Nexus / AWS ECR)
      │
      ▼ (deployment server pulls image)
Docker Container (running application)
```

#### Sample Dockerfile for a Java Application [GENERATED]

```dockerfile
FROM openjdk:17-jdk-slim          # Base image with Java 17

WORKDIR /app                      # Set working directory in container

COPY target/myapp-1.0.0.jar app.jar   # Copy the built JAR into container

EXPOSE 8080                       # Declare the port the app listens on

CMD ["java", "-jar", "app.jar"]   # Command to run on container start
```

#### Multi-Stage Docker Build [GENERATED]

Instead of building the JAR on your machine and copying it in, you can build entirely inside Docker, keeping the final image small:

```dockerfile
# Stage 1: Build
FROM maven:3.9-eclipse-temurin-17 AS builder
WORKDIR /build
COPY pom.xml .
COPY src ./src
RUN mvn clean package -DskipTests

# Stage 2: Run
FROM openjdk:17-jdk-slim
WORKDIR /app
COPY --from=builder /build/target/myapp.jar app.jar
EXPOSE 8080
CMD ["java", "-jar", "app.jar"]
```

Benefits of multi-stage builds:
- The final image contains only the runtime, not Maven, source code, or build tools.
- Much smaller image size (build environment is discarded).
- More secure (build secrets never end up in the final image).

#### Build Tools + Docker = Reproducible Environments [GENERATED]

Before Docker, "it works on my machine" was a common problem. Different Java versions, different OS, different environment variables caused builds to succeed locally but fail in production.

With Docker:
- The Dockerfile defines the exact environment (OS, Java version, dependencies).
- Any machine that runs the container gets the identical environment.
- The build tool ensures the artifact is consistent; Docker ensures the runtime is consistent.

---

## DELIVERABLE 4 — PYQ SOLUTIONS (Module 2 Only)

---

### PYQ SOURCE: ESE November 2025 (Main Paper — DevOps.PDF)

---

#### Q1(iii) — What is the role of version control systems (VCS) in DevOps? Give suitable example. [5 marks]

**Answer:**

A **Version Control System (VCS)** is a tool that tracks and manages changes to source code over time. In DevOps, VCS is the **foundation of the entire pipeline** — it is the starting point for automation.

**Role of VCS in DevOps:**

1. **Single Source of Truth**: All team members work from the same codebase. Every change is tracked. No more "which copy is the latest?" problems.

2. **Enables CI/CD Pipelines**: Every push to the repository triggers an automated pipeline (build → test → deploy). Without VCS, there is no event to trigger automation.

3. **Collaboration Without Conflict**: Multiple developers can work on different features (branches) simultaneously without interfering with each other.

4. **Rollback and Recovery**: If a deployment breaks production, a single command (`git revert`) rolls back to the last working version.

5. **Audit Trail**: Every change records: who made it, when, and why (commit message). This is essential for compliance and debugging.

6. **Environment Reproducibility**: The Dockerfile and infrastructure-as-code files are also stored in VCS, meaning the entire environment can be reproduced from the repository.

**Example**: A team uses Git (DVCS). Each developer works on a feature branch (`feature/payment-gateway`). When ready, they open a Pull Request. GitHub triggers a Jenkins pipeline that runs unit tests. If tests pass, the code is merged into `main`. Jenkins then automatically builds a Docker image and deploys to staging. This entire workflow is powered by Git as the VCS.

---

#### Q2B(ii) — Describe the architecture and functioning of a source code management system. [10 marks]

**Answer:**

**Source Code Management (SCM)** is a category of software tools that help manage changes to source code. Git is the most widely used SCM today.

**Architecture of a Git-based SCM System:**

```
  ┌─────────────────────────────────────────────────────┐
  │                 REMOTE LAYER                        │
  │  ┌──────────────────────────────────────────────┐   │
  │  │   Remote Repository (GitHub / GitLab / Nexus)│   │
  │  │   - Central server storing all code versions │   │
  │  │   - Accessible by all authorized team members│   │
  │  └──────────────────────────────────────────────┘   │
  └─────────────────────────────────────────────────────┘
                 git push ↑  ↓ git pull/clone
  ┌─────────────────────────────────────────────────────┐
  │                 LOCAL LAYER (each developer)        │
  │                                                     │
  │  Working Dir → [git add] → Staging → [git commit]  │
  │       │                      │              │       │
  │  (edit files)           (index/.git)  (.git/objects)│
  │                                                     │
  │  Local Repository (full copy of all history)        │
  └─────────────────────────────────────────────────────┘
```

**Key Components:**

1. **Working Directory**: Where developers edit files. Contains the checked-out version of the project.

2. **Staging Area (Index)**: An intermediate area that acts as a preview for the next commit. Developers selectively add changes here using `git add`. This allows committing only specific changes even if multiple files were modified.

3. **Local Repository (.git directory)**: Stored on the developer's machine. Contains the complete history of all commits, branches, and tags. Developers can commit, branch, and view history entirely offline.

4. **Remote Repository**: A shared server (GitHub, GitLab, Bitbucket, self-hosted). All team members push their local commits here and pull others' commits from here.

**How It Functions — Lifecycle:**

```
Step 1: Developer modifies files in the Working Directory.
Step 2: `git add <files>` → files are staged (snapshot taken).
Step 3: `git commit -m "message"` → staged snapshot is permanently stored
        in the Local Repository with a unique SHA-1 hash.
Step 4: `git push origin main` → local commits are sent to the Remote Repository.
Step 5: Other developers run `git pull` → they receive the latest commits.
Step 6: If conflicts arise (same lines edited by two developers),
        they are flagged and must be manually resolved.
```

**Core Data Structure:**

Git stores three types of objects:
- **Blob**: File content (a single version of a file).
- **Tree**: Directory structure (maps filenames to blobs).
- **Commit**: Points to a tree + metadata + parent commit SHA-1.

Every commit is identified by a 40-character SHA-1 hash computed from its content. This ensures integrity — any tampering changes the hash and is immediately detected.

**Benefits in a Team Environment:**
- Branching allows parallel development (feature, hotfix, release branches).
- Merging integrates completed work.
- History is immutable and fully auditable.
- Access control: who can push to which branch.

---

#### Q3(iii) — A Jenkins pipeline triggered by a Git commit failed because of a missing configuration file. (a) Analyze how Git hooks or branch protection rules could prevent such errors. (b) Suggest improvements to integrate Git and Jenkins effectively in the CI/CD pipeline. [10 marks]

**Answer:**

**(a) Git Hooks and Branch Protection Rules**

**Git Hooks** are scripts that execute automatically at specific points in Git's workflow. They can prevent problematic commits from ever reaching the remote repository.

| Hook | When it fires | Use for this problem |
|---|---|---|
| `pre-commit` | Before the commit is made | Check that required config files exist in the repo |
| `pre-push` | Before pushing to remote | Run a validation script to confirm config files are present |
| `commit-msg` | When writing commit message | Enforce commit message conventions (Jira ticket reference etc.) |

**Example pre-commit hook** (`.git/hooks/pre-commit`):
```bash
#!/bin/sh
# Fail the commit if config file is missing
if [ ! -f "src/main/resources/application.properties" ]; then
  echo "ERROR: Missing required config file: application.properties"
  exit 1
fi
```

This script runs before every commit. If the config file is missing, the commit is rejected locally before it even reaches Jenkins.

**Branch Protection Rules** (configured on GitHub/GitLab, not local):

- **Require status checks to pass**: The Jenkins CI build must succeed before a Pull Request can be merged into `main`. If the build fails due to a missing config, the PR is blocked.
- **Require pull request reviews**: A human reviewer can catch missing config files in code review.
- **Restrict direct pushes to `main`**: Developers cannot bypass CI by pushing directly.
- **Require branch to be up to date**: Forces developers to pull the latest main (which may have had config file changes) before merging.

**(b) Improvements to Git-Jenkins Integration**

1. **Use Webhooks instead of polling**: Configure GitHub to send a POST request to Jenkins as soon as a commit is pushed. Faster and more efficient than Jenkins periodically checking for changes.

2. **Validate configuration files in the pipeline itself**: Add an early validation stage in the Jenkinsfile:
   ```groovy
   pipeline {
     stages {
       stage('Validate Config') {
         steps {
           sh 'test -f src/main/resources/application.properties || exit 1'
         }
       }
       stage('Build') { ... }
       stage('Test') { ... }
       stage('Deploy') { ... }
     }
   }
   ```
   This fails fast — if the config is missing, the pipeline fails at the first stage with a clear error message, rather than deep into the build.

3. **Store config templates in Git**: Never rely on config files that exist only on a server. Put a template (`application.properties.template`) in Git. Secrets can be injected via Jenkins credentials or environment variables at runtime.

4. **Use Jenkins shared libraries**: Centralize pipeline code so changes to the validation logic apply to all pipelines instantly.

5. **Notifications**: Configure Jenkins to notify Slack/email on failure with the exact error message, so developers know immediately which config file is missing.

6. **Use multi-branch pipeline**: Jenkins automatically creates pipeline builds for every branch. Developers can test their branch's pipeline before merging to main.

---

### PYQ SOURCE: ESE with CO-BT Paper (same Nov 2025 cycle)

---

#### Q1(v) — Describe the benefits of using Git for version control. [5 marks, CO2, RE]

**Answer:**

Git is the most widely used version control system. Key benefits:

1. **Distributed Architecture**: Every developer has a complete local copy of the entire repository. Work can happen offline; the central server is not a single point of failure.

2. **Speed**: Most Git operations (commit, branch, diff, log) run locally without any network calls. Even for large repositories, operations complete in milliseconds.

3. **Branching and Merging**: Creating a branch in Git takes milliseconds (it is just a pointer). Developers can maintain separate feature branches, hotfix branches, and release branches without impacting each other.

4. **Data Integrity (SHA-1)**: Every commit is cryptographically hashed. Any unauthorized modification to history is immediately detectable. You can trust the repository content.

5. **Staging Area**: The ability to selectively stage changes means you can craft clean, focused commits even if multiple unrelated changes were made to the working directory.

6. **Full History**: Every change ever made is stored with author, timestamp, and reason. Debugging becomes easier — `git blame` shows who last changed each line; `git log` shows the complete evolution of the codebase.

7. **Undo Mistakes**: `git reset`, `git revert`, `git stash` provide multiple safety nets for undoing errors at different stages.

---

#### Q3(i) — Consider the following Git commit history diagram. Write a command and explain each: (a) Identify which branch HEAD is currently pointing to. (b) Explain which commits belong to the merge-conflict branch. (c) Write the Git command to merge another-piece-of-work into merge-conflict. (d) Explain what steps you would take if a merge conflict occurs. [10 marks, CO4, AP]

**Answer:**

Note: This question references a diagram shown in the exam. The diagram shows a standard Git divergent history with multiple branches. I will answer assuming a typical scenario:

```
  HEAD
   │
   ▼
  merge-conflict
   │
   ▼
  C5 ◄──── C4 ◄──── C2 ◄──── C1 ◄──── C0
                      ▲
                      └──── C3 ◄──── another-piece-of-work
```

**(a) Identifying HEAD**

In the diagram, HEAD points to the `merge-conflict` branch.

Command to verify:
```bash
$ git branch
* merge-conflict        # asterisk shows current branch (where HEAD is)
  another-piece-of-work
  master
```
Or: `$ git log --oneline --decorate` — the commit marked `(HEAD -> merge-conflict)` is the current position.

**(b) Commits on merge-conflict Branch**

The `merge-conflict` branch contains: **C0, C1, C2, C4, C5** (the chain of commits from the initial commit up through the branch tip at `merge-conflict`).

`another-piece-of-work` branched off at C2 and adds C3. So:
- `merge-conflict` branch: C0, C1, C2, C4, C5
- `another-piece-of-work` branch: C0, C1, C2, C3

**(c) Command to merge `another-piece-of-work` into `merge-conflict`**

First, ensure you are on the `merge-conflict` branch:
```bash
$ git checkout merge-conflict
```

Then merge:
```bash
$ git merge another-piece-of-work
```

Since both branches have diverged from C2 (one added C4/C5, the other added C3), Git will perform a **three-way merge** using C2 as the common ancestor.

**(d) Steps if a Merge Conflict Occurs**

```
Step 1: Identify conflicted files
$ git status
# Look for "both modified: <filename>"

Step 2: Open the conflicted file
$ vim index.html
# The file will contain conflict markers:
<<<<<<< HEAD
<line from merge-conflict branch>
=======
<line from another-piece-of-work branch>
>>>>>>> another-piece-of-work

Step 3: Edit the file — remove markers, keep the correct content
# (choose one version, combine both, or write something new)

Step 4: Stage the resolved file
$ git add index.html

Step 5: If multiple files are conflicted, repeat Steps 2-4 for each.

Step 6: Confirm all conflicts are resolved
$ git status
# Should show no more "both modified" entries

Step 7: Complete the merge with a commit
$ git commit -m "Merge another-piece-of-work into merge-conflict - resolved conflicts"
```

If at any point you want to abandon the merge:
```bash
$ git merge --abort       # Reverts to the pre-merge state
```

---

### PYQ SOURCE: Re-ISE (In-Semester Examination, July-November 2025)

---

#### Q3A — Analyze how Git supports Continuous Integration (CI) in a DevOps pipeline. [5 marks]

**Answer:**

**Continuous Integration (CI)** is the practice of automatically building and testing code every time a developer commits a change. Git is the enabler that makes CI possible.

**How Git supports CI:**

1. **Event-Driven Triggers**: When a developer runs `git push`, GitHub/GitLab sends a **webhook** (HTTP POST event) to the CI server (Jenkins, GitHub Actions). This automatically starts the CI pipeline — no human intervention needed.

2. **Branching for Isolation**: Each feature is developed in its own branch. The CI pipeline can run on every branch independently. Developers get feedback on their specific changes without affecting the main branch.

3. **Pull Requests as Quality Gates**: Before merging to `main`, a Pull Request triggers the CI pipeline. If tests fail, the merge is blocked. Only verified code reaches the main branch.

4. **History for Root Cause Analysis**: When a CI build fails, `git log` and `git blame` help identify which commit introduced the regression and who made the change.

5. **Rollback**: If a bad commit passes CI and breaks staging, `git revert <commit>` creates a new commit that undoes the change, which then triggers CI again to verify the revert is safe.

6. **Reproducibility**: The exact commit SHA-1 is recorded in the CI build log. Any team member can `git checkout <sha>` to reproduce the exact state that caused a failure.

**Example flow:**
```
Developer: git commit + git push to feature/login branch
                │
                ▼ (webhook)
          Jenkins CI starts:
          → git checkout feature/login
          → mvn clean test
          → Report: 47/47 tests pass ✓
          → Build artifact: login-feature-1.0.jar
                │
          PR opened → CI runs again on merged state
          → All checks pass → PR can be merged
```

Without Git, none of this automation is possible. Git provides the reliable, versioned, event-emitting source of truth that CI pipelines depend on.

---

### PYQ SOURCE: Sample Question Bank (Module 2 Questions)

---

#### Sample Q1 — Git Fundamentals: Differentiate between CVCS and DVCS. Explain the three states of a file in Git. [Long Answer]

**Differentiation between CVCS and DVCS:**

| Aspect | CVCS (e.g., SVN) | DVCS (e.g., Git) |
|---|---|---|
| Repository location | Single central server | Every developer has a full local copy |
| Internet required | Yes (for most operations) | No (commit, branch, log work offline) |
| Single point of failure | Yes (server down = no work) | No (any copy can restore the server) |
| Versioning scheme | Global incrementing number | SHA-1 hash per commit |
| Speed | Slow (network for most ops) | Fast (local for most ops) |
| Branching cost | Expensive (file copy) | Instantaneous (just a pointer) |
| Examples | SVN, CVS, Perforce | Git, Mercurial, Bazaar |

**Three States of a File in Git:**

```
┌─────────────────────────────────────────────────────────────────┐
│  Working Directory     Staging Area (.index)    Git Repository  │
│  ┌──────────────┐      ┌────────────────┐       ┌────────────┐  │
│  │  Modified    │─────►│    Staged      │──────►│ Committed  │  │
│  │  (changed,   │git   │  (snapshot     │ git   │ (permanent │  │
│  │   not staged)│ add  │   queued for   │commit │  in .git/) │  │
│  └──────────────┘      │   next commit) │       └────────────┘  │
│                         └────────────────┘                       │
└─────────────────────────────────────────────────────────────────┘
```

1. **Modified**: The file has been changed in the working directory but not yet staged. Git knows about it (it is tracked) but has not queued it for the next commit.

2. **Staged**: `git add` was run on the file. A snapshot of the current version is placed in the staging area. This is what will go into the next commit.

3. **Committed**: `git commit` was run. The staged snapshot is permanently and safely stored in the local Git database. It now has a SHA-1 hash identifier.

---

#### Sample Q2 — Git Branching Strategies: Explain git branch, checkout, merge, rebase. When to prefer rebase over merge?

**`git branch`**: Creates a new pointer (branch) to the current commit. Does not switch to the new branch.
```bash
$ git branch feature-x       # creates branch
$ git branch                 # lists all branches
$ git branch -d feature-x    # deletes branch
```

**`git checkout`**: Moves HEAD to a different branch/commit. Updates the working directory to match.
```bash
$ git checkout feature-x     # switch to branch
$ git checkout -b feature-x  # create + switch (shorthand)
```

**`git merge`**: Integrates changes from one branch into another. May create a merge commit (three-way) or simply move the pointer (fast-forward).
```bash
$ git checkout main
$ git merge feature-x        # merge feature-x into main
```

**`git rebase`**: Re-applies commits from one branch on top of another, rewriting commit history for a linear appearance.
```bash
$ git checkout feature-x
$ git rebase main            # replay feature-x commits on top of latest main
```

**When to prefer rebase over merge:**

- When you want a **clean, linear project history** without merge commits cluttering the log.
- When working on a **local feature branch** before opening a PR — rebasing onto the latest `main` ensures the PR has no conflicts and is up to date.
- When commits are still **local and not pushed** — safe to rewrite history.

**Never rebase** when the branch is **public (already pushed and shared with others)** — rewriting history causes major problems for teammates who have based work on those commits.

---

#### Sample Q3 — Merge Conflicts and Stashing: What causes a conflict? Steps to resolve? How is stash used for hotfixes?

**What causes a merge conflict:**

A merge conflict occurs when two branches have made changes to **the same lines of the same file** and Git cannot automatically determine which version to keep. Git knows both versions but needs a human to decide.

Also occurs when one branch deletes a file that the other branch modifies.

**Step-by-step conflict resolution:**

```
1. Attempt merge:
   $ git merge feature-branch
   # CONFLICT (content): Merge conflict in App.java

2. Identify conflicted files:
   $ git status
   # Both modified: App.java

3. Open file and look for conflict markers:
   <<<<<<< HEAD
   int timeout = 30;
   =======
   int timeout = 60;
   >>>>>>> feature-branch

4. Edit the file to the desired result:
   int timeout = 45;   # chosen value after team discussion

5. Remove all conflict markers (<<<<<<, =======, >>>>>>>).

6. Stage the resolved file:
   $ git add App.java

7. Commit to complete the merge:
   $ git commit -m "Merge feature-branch - resolved timeout conflict"
```

**Using git stash for urgent hotfixes:**

```
Scenario: Developer is 50% through feature X. Production bug reported.

1. Stash in-progress work:
   $ git stash push -m "WIP: feature X - half done"

2. Working directory is now clean. Switch to main:
   $ git checkout main

3. Create hotfix branch and fix the bug:
   $ git checkout -b hotfix/login-crash
   $ vim LoginService.java   # fix the bug
   $ git commit -a -m "Fix: null pointer in login flow"

4. Merge hotfix to main, push to production:
   $ git checkout main
   $ git merge hotfix/login-crash
   $ git push origin main

5. Delete hotfix branch:
   $ git branch -d hotfix/login-crash

6. Go back to feature work and restore stash:
   $ git checkout feature/feature-x
   $ git stash pop           # restores the stashed changes
```

---

#### Sample Q4 — Build Automation: Define it. Explain typical build stages for Java or JavaScript. [GENERATED]

**Definition:**

Build automation is the **scripted, repeatable process** of converting source code into a deployable artifact without manual intervention. It encompasses: dependency resolution, compilation, testing, packaging, and optionally, publishing and deployment.

**Typical Java Build Lifecycle (Maven):**

```
Source Code (src/main/java/*.java)
         │
         ▼ validate
Check project structure is valid
         │
         ▼ compile
javac *.java → *.class files (src → target/classes)
         │
         ▼ test
Run JUnit tests (src/test/java/*.java)
If any test fails → BUILD FAILURE (stop pipeline)
         │
         ▼ package
Assemble .class files + resources → myapp-1.0.jar / myapp.war
         │
         ▼ verify
Integration tests, code coverage checks (Jacoco)
         │
         ▼ install
Copy JAR to local Maven repository (~/.m2/)
         │
         ▼ deploy
Upload JAR to remote repository (Nexus/Maven Central)
```

Command: `mvn clean install` runs all phases up to install (clean = delete previous build output first).

**Typical JavaScript Build Lifecycle (npm):**

```
package.json (dependency list)
         │
         ▼ npm install
Downloads all packages from npm registry → node_modules/
         │
         ▼ npm run lint
Check code style (ESLint)
         │
         ▼ npm test
Run unit tests (Jest/Mocha)
         │
         ▼ npm run build
Webpack/Vite bundles JS → dist/bundle.js
         │
         ▼ npm publish (if library)
Upload package to npm registry
```

---

#### Sample Q5 — Artifact Publishing: What are artifacts? Why publish to a repository? [GENERATED]

**What are build artifacts:**

A **build artifact** is the compiled, packaged, deployable output of a build process. It is the binary form of software that can be deployed or distributed.

Examples:
- **JAR** (Java Archive): Compiled Java library or standalone application.
- **WAR** (Web Archive): Java web application containing servlets, JSPs, resources.
- **npm package**: Reusable JavaScript library published to npm registry.
- **Docker Image**: Containerized application (can be viewed as an artifact of a Dockerfile build).

**Why publishing to a repository is essential in DevOps:**

| Problem (without repo) | Solution (with artifact repo like Nexus) |
|---|---|
| JAR files shared via email/Slack | Single authoritative location; pull by URL |
| No version history | Every version stored with its exact SHA checksum |
| No access control | Role-based access (who can upload, who can download) |
| Different teams use different versions | All teams pull from the same repo |
| Cannot reproduce 6-month-old build | Every version permanently stored |
| Deployment server needs manual file copy | CI/CD pipeline pulls artifact by version automatically |

In a DevOps pipeline: Build tool creates the artifact → CI pipeline uploads to Nexus → Deployment pipeline downloads specific version from Nexus → Deployed to server. This is fully automated and auditable.

---

#### Sample Q6 — Build Tools and Docker: How are build tools integrated with Docker? Benefits of multi-stage builds? [GENERATED]

**Integration of Build Tools with Docker:**

The build tool (Maven/npm) and Docker work in a sequential pipeline:

```
1. Developer pushes to Git
2. Jenkins pulls the source code
3. Maven runs: mvn clean package → produces app.jar
4. Docker reads the Dockerfile and runs: docker build -t myapp:1.0 .
   (The Dockerfile COPYs the app.jar into the image)
5. Docker image pushed to registry: docker push registry/myapp:1.0
6. Deployment server pulls image and runs: docker run myapp:1.0
```

The build tool produces the artifact; Docker packages the artifact into a portable, isolated, runnable image.

**Benefits of Multi-Stage Docker Builds:**

A multi-stage build uses multiple `FROM` statements in a single Dockerfile. Earlier stages do the building; later stages copy only the outputs.

```dockerfile
# Stage 1: Build environment (has Maven, JDK, all dev tools)
FROM maven:3.9-eclipse-temurin-17 AS builder
WORKDIR /app
COPY pom.xml .
RUN mvn dependency:go-offline      # cache dependencies
COPY src ./src
RUN mvn clean package -DskipTests

# Stage 2: Runtime environment (minimal JRE only)
FROM eclipse-temurin:17-jre-alpine
WORKDIR /app
COPY --from=builder /app/target/myapp.jar app.jar
EXPOSE 8080
CMD ["java", "-jar", "app.jar"]
```

**Benefits:**

| Benefit | Explanation |
|---|---|
| **Smaller image** | Stage 2 has only JRE (~100MB) vs JDK + Maven (~600MB) |
| **Security** | Build tools, source code, and credentials never in final image |
| **Reproducible builds** | The build happens inside Docker; same result on any machine |
| **No local tooling required** | Developers don't need Maven installed locally — Docker does the build |
| **Clean separation** | Build environment vs runtime environment are explicitly distinct |

---

> **END OF DevOps MODULE 2 STUDY DOCUMENT**
>
> Summary of what is covered:
> - All syllabus topics with detailed explanation (Git VCS, Git internals, all Git operations, branching, merging, rebase, stash, conflicts, build tools, artifacts, Docker integration).
> - Complete PYQ solutions from: ESE Nov 2025 (main paper), ESE with CO-BT, ISE/MSE Re-exam, Sample Question Bank.
> - Build tool sections marked **[GENERATED]** as they were not in the provided notes.
> - All diagrams are text-based for exam reproduction.
