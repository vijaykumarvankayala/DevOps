# 🔧 Git – Useful Commands

This document lists **commonly used Git commands** for daily development, troubleshooting, and DevOps workflows.  
Use this as a **quick reference**, not a replacement for Git fundamentals.

---

## 📁 Repository Basics

### Clone a Repository
```bash
git clone <repo-url>
Check Repository Status
bash
Copy code
git status
View Configured Remotes
bash
Copy code
git remote -v
🌱 Branch Management
List Branches
bash
Copy code
git branch
git branch -a
Create a New Branch
bash
Copy code
git checkout -b feature/my-feature
Switch Branches
bash
Copy code
git checkout main
Delete a Branch
bash
Copy code
git branch -d feature/my-feature
git branch -D feature/my-feature   # force delete
✍️ Staging & Committing
Stage Files
bash
Copy code
git add file.txt
git add .
Commit Changes
bash
Copy code
git commit -m "feat: add login validation"
Amend Last Commit
bash
Copy code
git commit --amend
📤 Pushing & Pulling
Push Branch to Remote
bash
Copy code
git push origin feature/my-feature
Pull Latest Changes
bash
Copy code
git pull origin main
Fetch Without Merging
bash
Copy code
git fetch origin
🔍 Logs & History
View Commit History
bash
Copy code
git log
git log --oneline
View File History
bash
Copy code
git log file.txt
Show a Specific Commit
bash
Copy code
git show <commit-id>
🔄 Merging & Rebasing
Merge a Branch
bash
Copy code
git merge feature/my-feature
Rebase on Main
bash
Copy code
git rebase main
Abort Rebase
bash
Copy code
git rebase --abort
⚠️ Undo & Recovery (Very Important)
Undo Local Changes (Not Committed)
bash
Copy code
git checkout -- file.txt
Unstage a File
bash
Copy code
git reset file.txt
Reset to Previous Commit (Local Only)
bash
Copy code
git reset --soft HEAD~1
git reset --hard HEAD~1
Recover Lost Commits
bash
Copy code
git reflog
🏷 Tags & Releases
Create a Tag
bash
Copy code
git tag v1.0.0
Push Tags
bash
Copy code
git push origin v1.0.0
git push origin --tags
🧹 Cleanup & Maintenance
Remove Untracked Files
bash
Copy code
git clean -f
git clean -fd
Prune Deleted Remote Branches
bash
Copy code
git fetch --prune
🔐 Stashing Changes
Stash Work
bash
Copy code
git stash
List Stashes
bash
Copy code
git stash list
Apply Stash
bash
Copy code
git stash apply
📦 Comparing Changes
Compare Working Tree
bash
Copy code
git diff
Compare Staged Changes
bash
Copy code
git diff --staged
Compare Branches
bash
Copy code
git diff main..feature/my-feature
🚀 GitOps / CI-Friendly Commands
Verify Clean Working Tree
bash
Copy code
git diff --exit-code
Check Current Branch
bash
Copy code
git branch --show-current
🧠 Best Practices
Commit small, logical changes

Write meaningful commit messages

Avoid force-push on shared branches

Never commit secrets

Always pull before pushing

Prefer rebase for clean history

🚫 Dangerous Commands (Use with Caution)
bash
Copy code
git reset --hard
git push --force
git clean -fd
Only use these when you fully understand the impact.

🎯 Summary
Git enables safe collaboration, rollback, and auditability when used correctly.
This cheat sheet covers the most useful commands for daily development and DevOps workflows.
