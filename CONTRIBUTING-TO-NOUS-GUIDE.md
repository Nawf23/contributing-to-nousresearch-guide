# Complete Guide: Contributing to NousResearch (Mac & Windows)

> A beginner-friendly guide to making your first open-source contribution to NousResearch's Atropos project - no prior experience needed!

**Author:** [@Nawf23](https://github.com/Nawf23)  
**Last Updated:** March 2026

---

## Table of Contents
- [Introduction](#introduction)
- [What You'll Learn](#what-youll-learn)
- [Prerequisites](#prerequisites)
- [Setup Guide - Mac](#setup-guide---mac)
- [Setup Guide - Windows](#setup-guide---windows)
- [Making Your First Contribution](#making-your-first-contribution)
- [Common Issues & Solutions](#common-issues--solutions)
- [Next Steps](#next-steps)

---

## Introduction

NousResearch is a $70M funded AI research organization (backed by Paradigm and Delphi Capital) working on cutting-edge language models and reinforcement learning. Their Atropos project is open-source, and they welcome contributions from developers of all levels.

I recently made my first contribution with **zero prior open-source experience**, and I'm here to show you exactly how I did it - step by step.

**My contribution:** [PR #419](https://github.com/NousResearch/atropos/pull/419) - Added Python version clarification for Mac users

---

## What You'll Learn

By the end of this guide, you'll be able to:
- ✅ Set up a complete development environment
- ✅ Use Terminal/Command Line confidently
- ✅ Fork and clone repositories
- ✅ Create branches and make commits
- ✅ Push code to GitHub
- ✅ Submit professional Pull Requests
- ✅ Contribute to any open-source project

**Time needed:** 1-2 hours for first-time setup

---

## Prerequisites

### Required:
- A computer (Mac or Windows)
- Internet connection
- A GitHub account ([create one here](https://github.com/signup))
- 10-15GB free disk space
- Willingness to learn!

### Nice to have:
- Basic understanding of what GitHub is
- Familiarity with text editors

**Don't worry if you've never:**
- Used Terminal/Command Line
- Written code before
- Contributed to open-source

This guide assumes **zero prior knowledge**!

---

## Setup Guide - Mac

### Step 1: Open Terminal

<img width="826" height="403" alt="image" src="https://github.com/user-attachments/assets/b505c46a-2c56-41c4-b803-884acb4e8868" />


1. Press `Cmd + Space` (opens Spotlight)
2. Type "terminal"
3. Press Enter

**Pro tip:** Right-click Terminal in the dock → Options → Keep in Dock

### Step 2: Check What You Have

Run these commands to see what's already installed:

```bash
git --version
python3 --version
brew --version
code --version
```

<img width="697" height="142" alt="image" src="https://github.com/user-attachments/assets/7ad677c5-396a-4d38-900b-cd1e099aeeb8" />


**Expected output:**
- ✅ Git: Usually pre-installed on Mac
- ✅ Python: Mac comes with Python 3.9.6 (we'll upgrade this)
- ❌ Homebrew: Probably not installed
- ❌ VSCode: Probably not installed

### Step 3: Install Homebrew (Mac's Package Manager)

**What is Homebrew?** Think of it like an app store for developer tools.

Run this command:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

**What happens:**
1. It asks for your Mac password (you won't see it while typing - this is normal!)
2. Press Enter to confirm
3. Wait 3-5 minutes for installation
4. **Important:** At the end, it shows commands to add Homebrew to your PATH - **copy and run those exactly**

They'll look like:
```bash
echo >> /Users/yourname/.zprofile
echo 'eval "$(/opt/homebrew/bin/brew shellenv zsh)"' >> /Users/yourname/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv zsh)"
```

Verify installation:
```bash
brew --version
```

You should see: `Homebrew 5.x.x` or similar

### Step 4: Install Python 3.11

**Why?** NousResearch requires Python 3.10+, and Mac comes with 3.9.6.

```bash
brew install python@3.11
```

Wait 3-5 minutes. Then verify:

```bash
python3.11 --version
```

### Step 5: Install VSCode

Download from: [https://code.visualstudio.com/](https://code.visualstudio.com/)

1. Click "Download for Mac" (choose Apple Silicon if you have M1/M2/M3)
2. Open the downloaded file
3. Drag VSCode to Applications folder

**Enable the `code` command:**
1. Open VSCode
2. Press `Cmd + Shift + P`
3. Type "shell command"
4. Select "Shell Command: Install 'code' command in PATH"

Verify:
```bash
code --version
```

### Step 6: Configure Git

Replace with your actual GitHub info:

```bash
git config --global user.name "YourGitHubUsername"
git config --global user.email "your-email@example.com"
```

Verify:
```bash
git config --global user.name
git config --global user.email
```

### Step 7: Create GitHub Personal Access Token

**Why?** GitHub no longer accepts passwords for git operations. You need a token.

<img width="1170" height="555" alt="image" src="https://github.com/user-attachments/assets/af7d5461-3e84-44f4-bbe4-59bbebff963e" />


1. Go to [github.com](https://github.com) and log in
2. Click your profile picture → Settings
3. Scroll to bottom → Developer settings
4. Personal access tokens → Tokens (classic)
5. Generate new token (classic)
6. Name: "NousResearch Contributions"
7. Expiration: 90 days (or longer)
8. Check: **repo** (full control)
9. Click Generate token
10. **COPY THE TOKEN IMMEDIATELY** - you won't see it again!

**Save it in:** Notes app, password manager, or secure document

### Step 8: Create Project Folder

```bash
cd ~
mkdir github-projects
cd github-projects
pwd
```

You should see: `/Users/yourname/github-projects`

---

## Setup Guide - Windows

### Step 1: Install WSL (Windows Subsystem for Linux)

**What is WSL?** It lets you run Linux on Windows - essential for development.


1. Click Start
2. Type "PowerShell"
3. Right-click → Run as Administrator
4. Run:

```powershell
wsl --install
```

5. Restart your computer when prompted
6. After restart, Ubuntu will open automatically
7. Create a username and password (remember these!)


Verify:
```bash
wsl --version
```

### Step 2: Update Ubuntu and Install Tools

In your Ubuntu terminal:

```bash
sudo apt update
sudo apt upgrade -y
```

Install essential tools:

```bash
sudo apt install git python3 python3-pip python3-venv build-essential -y
```

Verify:
```bash
git --version
python3 --version
```


### Step 3: Install VSCode

Download from: [https://code.visualstudio.com/](https://code.visualstudio.com/)

1. Download "Windows" version
2. Install normally
3. **Important:** Install the **WSL extension** in VSCode

To open projects from WSL:
```bash
code .
```

### Step 4: Configure Git

In Ubuntu terminal:

```bash
git config --global user.name "YourGitHubUsername"
git config --global user.email "your-email@example.com"
```

### Step 5: Create GitHub Personal Access Token

**Follow the same steps as Mac (Step 7 above)**

### Step 6: Create Project Folder

In Ubuntu terminal:

```bash
cd ~
mkdir github-projects
cd github-projects
pwd
```

---

## Making Your First Contribution

**These steps are identical for Mac and Windows (if you're on Windows, use Ubuntu terminal)**

### Step 1: Fork the Repository

![IMG_9866](https://github.com/user-attachments/assets/80301947-2d5d-4a0e-b68b-2853c1f592bd)


1. Go to: [https://github.com/NousResearch/atropos](https://github.com/NousResearch/atropos)
2. Click **Fork** button (top right)
3. Wait for GitHub to create your copy

You now have: `https://github.com/YourUsername/atropos`

### Step 2: Clone Your Fork

```bash
cd ~/github-projects
git clone https://github.com/YourUsername/atropos.git
cd atropos
```

Replace `YourUsername` with your actual GitHub username.

### Step 3: Set Up Python Virtual Environment

**What is this?** An isolated Python environment so dependencies don't conflict.

**For Mac:**
```bash
python3.11 -m venv .venv
source .venv/bin/activate
```

**For Windows (WSL):**
```bash
python3 -m venv .venv
source .venv/bin/activate
```

**You should see `(.venv)` appear in your prompt!**

### Step 4: Install Dependencies

**⚠️ WARNING: This takes 15-30 minutes!**

```bash
pip install --upgrade pip
pip install -e ".[dev]"
```

**What happens:**
- Downloads and installs all required packages
- Your computer might get warm - this is normal!
- You'll see lots of text scrolling - don't panic!
- **On Mac M1/M2/M3:** Some packages need to compile for ARM - this is why it's slow


### Step 5: Install Pre-commit Hooks

```bash
pre-commit install
```

**What is this?** Automatic code quality checks before you commit.

### Step 6: Run Tests (Verify Setup)

```bash
pytest
```

If you see tests passing - **congratulations, your setup is complete!** 🎉

### Step 7: Create a Branch

**Never work directly on `main`!**

```bash
git checkout main
git pull origin main
git checkout -b docs/your-contribution-name
```

Example branch names:
- `docs/fix-typo-in-readme`
- `docs/add-windows-setup-guide`
- `docs/clarify-python-requirements`

### Step 8: Make Your Changes

Open VSCode:
```bash
code .
```

**Good first contributions:**
- Fix typos in `README.md` or `CONTRIBUTING.md`
- Improve unclear documentation
- Add examples to existing docs
- Clarify setup instructions

**Example edit:**

Press `Cmd + S` (Mac) or `Ctrl + S` (Windows) to save.

### Step 9: Commit Your Changes

```bash
git status
git add .
git commit -m "docs: fix typo in installation instructions"
```

**Commit message format:**
- Start with type: `docs:`, `feat:`, `fix:`
- Use present tense: "add" not "added"
- Be specific and concise

**Good examples:**
- ✅ `docs: clarify Python version requirement`
- ✅ `docs: fix typo in README`
- ✅ `docs: add troubleshooting section for M1 Macs`

**Bad examples:**
- ❌ `update stuff`
- ❌ `changes`
- ❌ `fixed things`

### Step 10: Push to GitHub

```bash
git push origin docs/your-contribution-name
```

**Authentication:**
- Username: Your GitHub username
- Password: **Paste your Personal Access Token** (NOT your GitHub password!)


### Step 11: Create Pull Request

1. Go to: [https://github.com/NousResearch/atropos](https://github.com/NousResearch/atropos)
2. You'll see a yellow banner: "Compare & pull request"
3. Click it

**Fill out the PR template:**

**Title:**
```
docs: add Python 3.10+ requirement note for Mac users
```

**Description:**
```markdown
## PR Type
- [x] Non-Environment PR - Complete Description, Related Issues & Type of Change sections

---

## 📝 General Information

### Description
[Clearly explain what you changed and why]

### Related Issues
[Link any relevant issues or explain the problem this solves]

### Type of Change
- [x] This change requires a documentation update

---

## Changes Made
- [Bullet point list of specific changes]

## Motivation
[Why is this change helpful? What problem does it solve?]

## Testing
- [How did you test this? What did you verify?]
```

Click **Create pull request**

---

## Common Issues & Solutions

### Issue 1: "command not found: brew" (Mac)

**Solution:**
```bash
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
source ~/.zprofile
```

### Issue 2: "requires Python >=3.10" error

**Mac:**
```bash
brew install python@3.11
python3.11 -m venv .venv
source .venv/bin/activate
```

**Windows:**
```bash
sudo apt install python3.11 python3.11-venv
python3.11 -m venv .venv
source .venv/bin/activate
```

### Issue 3: Virtual environment won't activate

**Check you're in the right directory:**
```bash
pwd
cd ~/github-projects/atropos
source .venv/bin/activate
```

### Issue 4: Git push asks for password repeatedly

**You're using GitHub password instead of token!**
- Use your **Personal Access Token** as the password
- Token starts with `ghp_`

### Issue 5: "pip install" fails with build errors

**Mac:**
```bash
xcode-select --install
pip install --upgrade pip setuptools wheel
```

**Windows:**
```bash
sudo apt install build-essential python3-dev
```

### Issue 6: Pre-commit checks fail

**Run the checks manually to see details:**
```bash
pre-commit run --all-files
```

Fix the issues it reports, then commit again.

### Issue 7: Out of disk space

**Check space:**
```bash
df -h
```

**Clean up:**
```bash
# Mac
brew cleanup

# Windows
sudo apt autoremove
sudo apt clean
```

---

### After Your First PR

1. **Wait for review** - maintainers will respond (usually within a few days)
2. **Address feedback** if requested
3. **Celebrate when it's merged!** 

### Mac/Linux Terminal Basics
```bash
pwd                    # Where am I?
ls                     # What's here?
cd folder_name         # Go into folder
cd ..                  # Go up one level
cd ~                   # Go home
mkdir folder_name      # Create folder
code .                 # Open VSCode
clear                  # Clean screen
```

## Connect With Me

- **GitHub:** [@Nawf23](https://github.com/Nawf23)
- **Twitter/X:** [@victornawf2]

Found this guide helpful? ⭐ Star this repo and share it with others!

Have questions or suggestions? Open an issue or submit a PR!

---
