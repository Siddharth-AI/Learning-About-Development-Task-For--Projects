# 🚀 Developer Setup Guide for Windows

This comprehensive guide walks you through setting up Git, SSH, Git Flow, Oh My Posh, Nerd Font, and NVM on Windows for an efficient development experience.

---

## 🔐 1. Generate SSH Key for GitHub

```bash
ssh-keygen
```

> 📌 Your key will be saved to:
> `C:\Users\<YourUsername>\.ssh\id_rsa.pub`

1. Open the above file.
2. Copy its content.
3. Go to **GitHub → Settings → SSH and GPG Keys → New SSH Key**.
4. Paste the key and save.

---

## 🛡️ 2. Enable PowerShell Script Execution

To allow custom scripts to run in PowerShell:

1. Run PowerShell as **Administrator**.
2. Execute the following:

```powershell
Set-ExecutionPolicy RemoteSigned
```

---

## 🍫 3. Install Git using Chocolatey

### Step 1: Install Chocolatey

```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force; \
[System.Net.ServicePointManager]::SecurityProtocol = \
[System.Net.ServicePointManager]::SecurityProtocol -bor 3072; \
iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```

### Step 2: Install Git

```bash
choco install git
```

---

## 🧰 4. Common Git Commands Explained

| Command                                  | Description                                       |
| ---------------------------------------- | ------------------------------------------------- |
| `git init`                               | Initialize a new Git repository                   |
| `git status`                             | Show status of working directory and staging area |
| `git add .`                              | Stage all modified files                          |
| `git add <file>`                         | Stage a specific file                             |
| `git commit -m "message"`                | Save changes to local repo with a message         |
| `git log`                                | View commit history                               |
| `git branch`                             | List all branches                                 |
| `git branch <name>`                      | Create a new branch                               |
| `git checkout <branch>`                  | Switch to a branch                                |
| `git checkout -b <name>`                 | Create and switch to a new branch                 |
| `git merge <branch>`                     | Merge given branch into current branch            |
| `git pull`                               | Download and integrate remote changes             |
| `git push`                               | Upload commits to remote repo                     |
| `git push -u origin <branch>`            | Push branch and track it remotely                 |
| `git remote -v`                          | View remote repo URLs                             |
| `git clone <url>`                        | Clone a remote repo locally                       |
| `git config --global user.name "Name"`   | Set Git username globally                         |
| `git config --global user.email "Email"` | Set Git email globally                            |
| `git branch -d <name>`                   | Delete a branch (if merged)                       |
| `git stash`                              | Temporarily save changes                          |
| `git stash pop`                          | Apply saved stash changes                         |

---

## 🌱 5. Git Flow Installation on Windows

### Step 1: Install Git Flow (AVH edition)

```bash
choco install git-flow-avh
```

### Step 2: Initialize Git Flow

```bash
git flow init
```

> Press **Enter** to accept default branch naming conventions.

---

## 🔄 6. Git Flow Commands & Descriptions

| Command                               | Description                                                               |
| ------------------------------------- | ------------------------------------------------------------------------- |
| `git flow init`                       | Initialize Git Flow in the repository                                     |
| `git flow feature start <name>`       | Start a new feature from `develop` branch                                 |
| `git flow feature finish <name>`      | Merge feature into `develop` and delete feature branch                    |
| `git flow feature publish <name>`     | Push feature branch to remote                                             |
| `git flow feature pull origin <name>` | Pull a feature branch from remote                                         |
| `git flow release start <version>`    | Start a release branch from `develop`                                     |
| `git flow release finish <version>`   | Merge into `main` and `develop`, tag, then delete                         |
| `git flow release publish <version>`  | Push release branch to remote                                             |
| `git flow hotfix start <name>`        | Start a hotfix branch from `main`                                         |
| `git flow hotfix finish <name>`       | Merge hotfix into `main` and `develop`, tag, then delete                  |
| `git flow support start <name>`       | Create long-term support branch (rarely used)                             |
| `git flow bugfix start <name>`        | Start a bugfix branch (optional; requires enabling bugfix in flow config) |
| `git flow bugfix finish <name>`       | Finish and merge bugfix back to `develop`                                 |

> 🧠 Git Flow enforces structure and is ideal for organized release processes.

---

## 🎨 7. Install Oh My Posh

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

1. Open **Environment Variables** settings.
2. Edit the `Path` under **User Variables**.
3. Click **New** and add:

`C:\Users\<YourUsername>\AppData\Local\Programs\oh-my-posh\bin`

---

## 📂 9. Auto-Load Theme in PowerShell

Create the file if it doesn't exist:

`C:\Users\<YourUsername>\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1`

Add a theme configuration:

**Default Theme:**

```powershell
oh-my-posh init pwsh --config "$env:POSH_THEMES_PATH\jandedobbeleer.omp.json" | Invoke-Expression
```

**Better Theme (optional):**

```powershell
oh-my-posh init pwsh --config "$env:POSH_THEMES_PATH\1_shell.omp.json" | Invoke-Expression
```

---

## 🔤 10. Install Nerd Font (JetBrainsMono)

1. Go to: [https://www.nerdfonts.com/font-downloads](https://www.nerdfonts.com/font-downloads)
2. Download **JetBrainsMono Nerd Font**
3. Extract `.zip` and copy all `.ttf` files
4. Paste them in:

```
C:\Windows\Fonts
```

---

## 🌱 11. Install NVM (Node Version Manager)

1. Visit: [https://github.com/coreybutler/nvm-windows/releases](https://github.com/coreybutler/nvm-windows/releases)
2. Download `nvm-setup.exe`
3. Install and follow on-screen instructions
4. Add this to environment variables:

`C:\Users\<YourUsername>\AppData\Local\nvm`

---

## ✅ You're All Set!

You now have a complete Windows developer setup with Git, Git Flow, Oh My Posh, and Nerd Fonts. Happy coding! 💻
