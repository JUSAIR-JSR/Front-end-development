📘 Git & GitHub Course — Beginner to Advanced

Version: 2025 • Full Git + GitHub + Branching + Pull Requests + GitHub Pages

📚 Table of Contents

What is Git?

What is GitHub?

Install Git

Configure Git

Create your first repository

Basic Git commands (add, commit, push)

Branching

Merging

Resolving merge conflicts

GitHub basics

Fork, Clone, Pull Request

GitHub Pages hosting

.gitignore

Undoing changes

Git log & history

SSH Key setup

Git workflow for teams

Real-world projects

Cheat sheet

1️⃣ What is Git?

Git is a version control system used to track changes in your code.

✔ Saves versions
✔ Allows collaboration
✔ Manages branches
✔ Prevents file loss

2️⃣ What is GitHub?

GitHub is a cloud platform for storing Git repositories and collaborating with others.

✔ Store code
✔ Open-source projects
✔ Issues & PRs
✔ CI/CD
✔ GitHub Pages

3️⃣ Install Git

Download:
https://git-scm.com/downloads

Check version:

git --version

4️⃣ Configure Git
git config --global user.name "Your Name"
git config --global user.email "your@email.com"


Check config:

git config --list

5️⃣ Create Your First Repository
Option A — Local repo
mkdir myproject
cd myproject
git init

Option B — GitHub → New Repo

Then clone:

git clone https://github.com/user/repo.git

6️⃣ Basic Git Commands
Check status
git status

Add files
git add .

Commit
git commit -m "Initial commit"

Add remote URL
git remote add origin https://github.com/user/repo.git

Push to GitHub
git push -u origin main

7️⃣ Branching

Create a branch:

git branch feature-login


Switch branch:

git checkout feature-login


Create + switch:

git checkout -b feature-login


List branches:

git branch


Delete branch:

git branch -d feature-login

8️⃣ Merging

Switch to main:

git checkout main


Merge another branch:

git merge feature-login

9️⃣ Resolve Merge Conflicts

When Git shows conflict markers:

<<<<<<< HEAD
Your code
=======
Incoming code
>>>>>>> feature-login


Edit manually → save → commit.

🔟 GitHub Basics
Create new repository

GitHub → New → Repo name → Public/Private

How to push local project first time
git init
git add .
git commit -m "first commit"
git branch -M main
git remote add origin URL
git push -u origin main

1️⃣1️⃣ Clone, Fork & Pull Request
Clone
git clone repo_url

Fork

Makes a copy of someone else’s repo into your account.

Pull Request (PR)

Used to contribute to repos.

Steps:

Fork repo

Clone fork

Create branch

Make changes

Push branch

Create PR

Owner reviews merges

1️⃣2️⃣ GitHub Pages Hosting
Step 1: Create a repo with name:
username.github.io

Step 2: Add index.html
Step 3: Push the code

The site becomes live at:

https://username.github.io

OR for project pages

GitHub → Settings → Pages → Select main branch → Save.

1️⃣3️⃣ .gitignore

Ignore files you don’t want to commit:

node_modules/
env/
dist/
*.log


Create file:

touch .gitignore

1️⃣4️⃣ Undoing Changes

Reset staged files:

git reset .


Undo last commit:

git reset HEAD~1


Hard reset (dangerous):

git reset --hard HEAD~1

1️⃣5️⃣ Git Log & History

Show history:

git log


Pretty log:

git log --oneline --graph --decorate

1️⃣6️⃣ SSH Key Setup (Avoid Login Every Time)

Generate key:

ssh-keygen -t ed25519 -C "your@email.com"


Copy key:

cat ~/.ssh/id_ed25519.pub


Add to GitHub → Settings → SSH keys

Test:

ssh -T git@github.com

1️⃣7️⃣ Git Workflow for Teams
Standard Team Workflow
main → production ready
dev → active development
feature branches → new features


Example:

git checkout -b feature-login
git add .
git commit -m "done login"
git push origin feature-login


Then open Pull Request → merge to dev or main.

1️⃣8️⃣ Real World Git Project Example
Student Management System

Branches:

main

feature-login

feature-crud

bugfix-insert

ui-update

Team workflow:

Create branch

Push

PR

Review

Merge

1️⃣9️⃣ Git Commands Cheat Sheet
Task	Command
Initialize	git init
Add files	git add .
Commit	git commit -m ""
Push	git push
Clone	git clone URL
Create branch	git checkout -b dev
Merge	git merge dev
Delete branch	git branch -d dev
Undo commit	git reset HEAD~1
Show log	git log
Show graph	git log --oneline --graph