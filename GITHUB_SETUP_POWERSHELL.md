# Setup GitHub and local repository — PowerShell

Use this guide for the new repository only. Do not run these commands inside the old repository by accident.

## 1. Prerequisites

Install Git for Windows. Install supported Node.js and Python versions only after the project stack decision is confirmed. Optional: GitHub CLI (gh) for creating the remote repository from PowerShell.

Open PowerShell and verify:

    git --version
    gh --version

If GitHub CLI is not installed, create the repository in the GitHub website and use the Git remote commands below.

## 2. Extract to a new folder

Example path; replace it with your preferred location:

    New-Item -ItemType Directory -Force -Path "D:\Projects\RubroRAG-Thesis"
    Expand-Archive -Path "$HOME\Downloads\rubrorag-thesis-repository-starter.zip" -DestinationPath "D:\Projects\RubroRAG-Thesis" -Force
    Set-Location "D:\Projects\RubroRAG-Thesis"

Check that README.md, AGENTS.md, context, docs and GITHUB_SETUP_POWERSHELL.md are at the repository root. Do not accidentally create a nested folder and initialize Git in its parent.

## 3. Inspect before first commit

    git status
    Get-ChildItem -Force

Read .gitignore. Do not place a real .env, API key, password, production database, personal data, raw restricted research data or browser profile in this starter folder.

Initialize Git:

    git init -b main
    git status
    git add .
    git diff --cached --stat
    git diff --cached

Review the staged list carefully. If it includes a secret or unapproved data, stop and unstage/remove that file before proceeding.

Create the first commit:

    git commit -m "docs: establish thesis project foundation"

If Git asks for identity, configure the identity you want recorded in commits:

    git config --global user.name "Your Name"
    git config --global user.email "your-github-email@example.com"

## 4. Create a private GitHub repository

Recommended: create a Private repository because this is an academic project and the future data/code may have restrictions. Do not upload data you are not authorized to publish.

Option A — GitHub CLI:

    gh auth login
    gh repo create rubrorag-thesis --private --source . --remote origin --push

Choose the correct GitHub account when authenticating. Check that the repository URL and owner are correct before confirming.

Option B — GitHub website:

1. Sign in to GitHub.
2. Create a new repository named rubrorag-thesis.
3. Set visibility to Private.
4. Do not initialize the remote with a README, license, or .gitignore because this local repository already contains its own first commit.
5. Copy the repository's HTTPS URL.
6. In PowerShell from the project root:

    git remote add origin https://github.com/YOUR-USERNAME/rubrorag-thesis.git
    git remote -v
    git push -u origin main

Replace YOUR-USERNAME and repo name. Never paste a personal access token into a source file or command that is saved into shell history.

## 5. Verify

    git status
    git log -1 --oneline
    git remote -v
    git branch --show-current

Expected: main is tracked by origin/main and working tree is clean. Confirm the files appear on GitHub.

## 6. Feature workflow

For each feature, start from the latest clean main:

    git switch main
    git pull --ff-only
    git switch -c feat/F00-project-foundation

Ask Codex to implement only the referenced spec. Review:

    git diff --check
    git status
    git diff

Run the exact scripts defined by the project. Stage explicit files when practical, inspect the staged diff, then commit and push:

    git add path/to/reviewed-file
    git diff --cached
    git commit -m "feat: establish project foundation"
    git push -u origin feat/F00-project-foundation

Open a Pull Request, review, merge only when quality gates pass, then switch back to main and pull. Use a new branch for the next feature. Do not keep accumulating unrelated tasks in one feature branch.

## 7. Branch and repository protection

After initial CI exists, consider enabling branch protection/rulesets for main: require pull requests, required CI checks, and block force pushes/deletions. Do not require a CI status check before that check actually exists or it can block all merges.

## 8. Secret/data hygiene

- Keep .env files local; commit only .env.example with placeholder values.
- If a secret was ever committed, removing it in a later commit is not enough. Revoke/rotate it and follow GitHub's secret-removal guidance.
- Review raw research data, answer sheets, exports and screenshots before committing.
- Use Git LFS only for authorized large binary artifacts when appropriate; do not use GitHub as a dumping ground for all raw data.
- Do not run git clean -fd as a cleanup shortcut.
