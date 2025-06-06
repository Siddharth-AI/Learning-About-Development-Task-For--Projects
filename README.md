# 🚀 Developer Setup Guide (Windows)

This guide helps you set up Git, SSH, Git Flow, Oh My Posh, and JetBrainsMono Nerd Font on Windows for a smooth terminal and GitHub workflow.

---

## 🔐 1. Generate SSH Key for GitHub

```bash
ssh-keygen
```

> 📌 Note the path:  
> `C:\Users\<YourUsername>\.ssh\id_rsa.pub`

- Open the file and copy its contents.
- Go to **GitHub → Settings → SSH and GPG Keys** → **New SSH Key** → Paste and Save.

---

## 🛡️ 2. Enable Script Execution in PowerShell

Run PowerShell as **Administrator** and execute:

```powershell
Set-ExecutionPolicy RemoteSigned
```

---

## 🍫 3. Install Git via Chocolatey

### Step 1: Install Chocolatey

```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force; `
[System.Net.ServicePointManager]::SecurityProtocol = `
[System.Net.ServicePointManager]::SecurityProtocol -bor 3072; `
iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```

### Step 2: Install Git

```bash
choco install git
```

---

## 🧰 4. Common Git Commands (with Explanation)

| Command                                  | Description                                                  |
| ---------------------------------------- | ------------------------------------------------------------ |
| `git init`                               | Initialize a new Git repository                              |
| `git status`                             | Show the status of changes as untracked, modified, or staged |
| `git add .`                              | Stage all changes in the directory for commit                |
| `git add <file>`                         | Stage a specific file for commit                             |
| `git commit -m "msg"`                    | Commit staged changes with a message                         |
| `git log`                                | Show commit history                                          |
| `git branch`                             | List all branches                                            |
| `git branch <name>`                      | Create a new branch                                          |
| `git checkout <branch>`                  | Switch to a specific branch                                  |
| `git checkout -b <name>`                 | Create and switch to a new branch                            |
| `git merge <branch>`                     | Merge a branch into the current branch                       |
| `git pull`                               | Fetch and merge changes from the remote repository           |
| `git push`                               | Push local changes to the remote repository                  |
| `git push -u origin <branch>`            | Push branch and set upstream for tracking                    |
| `git remote -v`                          | Show remote repository URLs                                  |
| `git clone <url>`                        | Clone a repository from a URL                                |
| `git config --global user.name "Name"`   | Set Git global username                                      |
| `git config --global user.email "Email"` | Set Git global email                                         |
| `git branch -d <name>`                   | Delete a local branch (if merged)                            |
| `git stash`                              | Temporarily save uncommitted changes                         |
| `git stash pop`                          | Re-apply the latest stashed changes                          |

---

## 🌱 5. Install Git Flow on Windows

### Step 1: Install Git Flow via Chocolatey

```bash
choco install git-flow-avh
```

> 📦 This installs the AVH edition of Git Flow, which is the most up-to-date version.

### Step 2: Initialize Git Flow in a Repository

```bash
git flow init
```

You will be prompted to set naming conventions for branches. You can press **Enter** to accept defaults.

---

## 🔄 6. Git Flow Commands (and What They Do)

| Command                             | Description                                      |
| ----------------------------------- | ------------------------------------------------ |
| `git flow init`                     | Initialize Git Flow in your repo                 |
| `git flow feature start <name>`     | Start a new feature branch                       |
| `git flow feature finish <name>`    | Finish the feature and merge to develop          |
| `git flow release start <version>`  | Start a release branch                           |
| `git flow release finish <version>` | Finish release (merge to main & develop) and tag |
| `git flow hotfix start <name>`      | Start a hotfix from main                         |
| `git flow hotfix finish <name>`     | Finish hotfix (merge to main & develop) and tag  |
| `git flow support start <name>`     | Start a support branch (rarely used)             |

> Git Flow helps you manage long-term projects with structured branching: `feature`, `release`, `hotfix`, and `support`.

---

## 🎨 7. Install Oh My Posh (Terminal Themes)

### Option 1: Chocolatey

```bash
choco install oh-my-posh
```

### Option 2: Winget

```bash
winget install JanDeDobbeleer.OhMyPosh -s winget
```

---

## 🔧 8. Add Oh My Posh to PATH

1. Open **Environment Variables** (Win + S → Search it).
2. Edit **User `Path`** → Click **New** and add:

```
C:\Users\<YourUsername>\AppData\Local\Programs\oh-my-posh\bin
```

---

## 📂 9. Auto-Load Theme in PowerShell

Create file (if not exists):

```
C:\Users\<YourUsername>\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1
```

Add one of the following lines:

**Default Theme:**

```powershell
oh-my-posh init pwsh --config "$env:POSH_THEMES_PATH\jandedobbeleer.omp.json" | Invoke-Expression
```

**Alternative Theme:**

```powershell
oh-my-posh init pwsh --config "$env:POSH_THEMES_PATH\1_shell.omp.json" | Invoke-Expression
```

---

## 🔤 10. Install Nerd Font (JetBrainsMono)

1. Visit: [https://www.nerdfonts.com/font-downloads](https://www.nerdfonts.com/font-downloads)
2. Download **JetBrainsMono Nerd Font**.
3. Extract ZIP → Copy all `.ttf` files.
4. Paste into:

```
C:\Windows\Fonts
```

---

## ✅ You're all set! Now enjoy a powerful, customized terminal and structured Git/Git Flow development workflow 🎉

## 📘 11. Git Flow Full Command Reference

| Command                               | Description                                                                                       |
| ------------------------------------- | ------------------------------------------------------------------------------------------------- |
| `git flow init`                       | Initialize Git Flow in your repository with default or custom branch names.                       |
| `git flow feature start <name>`       | Creates a new feature branch from `develop` and checks it out.                                    |
| `git flow feature finish <name>`      | Finishes the feature: merges it back into `develop` and deletes the feature branch.               |
| `git flow feature publish <name>`     | Pushes the feature branch to the remote repository.                                               |
| `git flow feature pull origin <name>` | Pulls the feature branch from remote and checks it out locally.                                   |
| `git flow release start <version>`    | Starts a release branch from `develop`. Useful for preparing a production release.                |
| `git flow release finish <version>`   | Finishes the release: merges into `main` and `develop`, tags the release, and deletes the branch. |
| `git flow release publish <version>`  | Pushes the release branch to the remote.                                                          |
| `git flow release track <version>`    | Tracks a remote release branch.                                                                   |
| `git flow hotfix start <name>`        | Creates a hotfix branch from `main` to fix something urgent in production.                        |
| `git flow hotfix finish <name>`       | Finishes the hotfix: merges into `main` and `develop`, tags it, and deletes the branch.           |
| `git flow support start <name>`       | Creates a support branch, used for long-term support. (Rarely used in most projects.)             |
| `git flow bugfix start <name>`        | Start a bugfix from `develop` (if bugfix option is enabled in init).                              |
| `git flow bugfix finish <name>`       | Finish and merge a bugfix back into `develop`.                                                    |

> 🧠 Git Flow provides a standard branching model for managing releases and features, ensuring clean merges and controlled deployment.
