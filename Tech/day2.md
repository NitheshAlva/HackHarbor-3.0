---
day: 2
title: "CLI Basics + GIT"
description: "Covers basics of CLI and helps students get started with git"
---

# Day 2 - CLI Basics + GIT

## Mentor's Guide
> Jump to [introduction](#Introduction)
### Before Class:

* Ensure Git is installed on all systems
* Verify access to GitHub accounts

### In-Class Tips:

* Begin with a quick live demo of using `cd`, `dir`, and `mkdir`
* Let students try a few commands on their own
* Explain version control with real-world analogies (e.g., saving versions of an essay)
* Walk through the Git workflow step-by-step and check progress at each stage
* Pair up students if anyone falls behind

> [!WARNING]  
> Do not forget to teach about connecting git with github. And please use SSH for authentication

### After Class:

* Ask students to create another Git repo for practice
* Encourage use of GitHub for storing code taught during internship period
* Suggest optional reading: GitHub Docs or try.github.io interactive tutorial

---

## Introduction

Welcome to Day 2 of our course! Today, we will explore the **Command Line Interface (CLI)** — a powerful way to interact with your computer — and **Git**, a version control system that developers use to manage their code and collaborate efficiently.

---

## CLI Basics

### What is a Terminal?

A **terminal** (or command-line interface, CLI) is a text-based interface that allows users to interact with the operating system using commands instead of graphical user interfaces (GUIs). It's especially useful for developers, sysadmins, and power users.

> In Windows, the terminal is commonly accessed via **Command Prompt** or **Windows Terminal** (recommended for a modern experience).

---

### Important CLI Commands (Windows)

| Command | Description |
|--------|-------------|
| `cd` | Change directory |
| `dir` | List files and folders in the current directory (Windows alternative to `ls`) |
| `cls` | Clear the terminal screen |
| `echo` | Print a message |
| `mkdir` | Make a new directory |
| `rmdir` or `del` | Remove a directory or file |
| `exit` | Exit the terminal |

#### Examples:

```bash
cd Documents        # Go to the Documents folder
mkdir projects      # Create a folder named 'projects'
cd projects         # Navigate into 'projects'
echo Hello World!   # Print Hello World!
cls                 # Clear the screen
````

> Note: On Linux/macOS, `ls` is used instead of `dir`, and `clear` instead of `cls`.

---

## Git Basics

### What is Git?

**Git** is a free and open-source **version control system**. It helps developers track changes in code, collaborate with others, and roll back to previous versions if needed.

> Created by Linus Torvalds (also creator of Linux), Git is the most widely used version control system in the world.

---

### Introduction to Git

Git lets you:

* Track the history of changes in files.
* Work on new features in **branches**.
* Merge changes safely with others.
* Contribute to projects collaboratively via platforms like **GitHub**, **GitLab**, etc.

<div style="text-align: center;">
  <img src="./assets/Git_workflow.jpg" alt="Git Workflow" width="500">
</div>

---

### Getting Started with Git

Before using Git, configure your identity:

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

---

### Setting Up Authentication

It's recommended to use **SSH instead of HTTPS**, as it avoids repeated login prompts and simplifies authentication in the long run.

Helpful resources:

* 📘 [Setting up Git (The Odin Project)](https://www.theodinproject.com/lessons/foundations-setting-up-git)
* 🎥 [Video Guide](https://youtu.be/snCP3c7wXw0?si=Bw8ulNhQBEVxC2yc)

---

#### 1. Generate an SSH Key (Git Bash)

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

* Press **Enter** to accept the default file location.
* Press **Enter** again to skip setting a passphrase.

---

#### 2. Start the SSH agent and add your key

**In Git Bash:**

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

**In PowerShell (Run as Administrator the first time):**

```powershell
Set-Service ssh-agent -StartupType Automatic
Start-Service ssh-agent
ssh-add $env:USERPROFILE\.ssh\id_ed25519
```

---

#### 3. Add the SSH key to GitHub

1. Display your public key: (in Git bash)

   ```bash
   cat ~/.ssh/id_ed25519.pub
   ```

2. Copy the entire output.

3. Go to [https://github.com/settings/keys](https://github.com/settings/keys)

4. Click **"New SSH key"**, paste the key, and give it a descriptive title (e.g., *"Windows laptop"*).

---

### Initialize Git in Your Project

Navigate to your project folder and run:

```bash
cd your-project-folder
git init
```

This creates a `.git` directory that allows Git to track changes in your project.

---

### Git Basic Commands

| Command                       | Description                                      |
| ----------------------------- | ------------------------------------------------ |
| `git init`                    | Initializes a new Git repository                 |
| `git status`                  | Shows current changes (staged/unstaged)          |
| `git add <file>`              | Stages a file for commit                         |
| `git commit -m "message"`     | Saves staged changes with a message              |
| `git log`                     | Shows commit history                             |
| `git remote add origin <url>` | Links your local repo to a remote (like GitHub)  |
| `git push -u origin main`     | Pushes commits to the remote repo                |
| `git pull`                    | Gets latest changes from the remote repo         |
| `git clone <url>`             | Copies a remote repository to your local machine |

#### Example Git Workflow:

```bash
git init
git add index.html
git commit -m "Add homepage"
git remote add origin https://github.com/username/repo.git
git push -u origin main
```

---

## Follow-Along Task

Let's try this together!

### Task: Initialize and Push Your First Git Repo

1. Open Windows Terminal and go to your desktop:

```bash
cd Desktop
```

2. Create a new folder and move into it:

```bash
mkdir my-first-git-project
cd my-first-git-project
```

3. Create a sample file:

```bash
echo Hello Git! > readme.txt
```

4. Initialize Git:

```bash
git init
```

5. Add and commit the file:

```bash
git add readme.txt
git commit -m "Initial commit with readme"
```

6. (Optional) Create a repository on GitHub, then link it and push:

```bash
git remote add origin https://github.com/yourusername/my-first-git-project.git
git push -u origin main
```

---

## Summary

Today, you learned:

* What a terminal is and how to navigate using CLI.
* Key Windows CLI commands.
* What Git is and why it's useful.
* How to set up and use Git for version control.
* A hands-on example pushing your first project to GitHub.
