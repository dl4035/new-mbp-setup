# 🍎 New MacBook Pro Setup Guide

A personal checklist and command reference for setting up a clean, lean, and secure MBP — optimized for dev use with minimal bloat.

---

## 1. Install Homebrew

Run this in Terminal and press `RETURN` when prompted:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

> ⚠️ This will also install **Xcode Command Line Tools** — let it finish before moving on.

After the installer completes, add Homebrew to your PATH:

```bash
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
```

Verify it works:

```bash
brew doctor
```

---

## 2. Install Dev Tools

Run each line **individually**:

```bash
brew install git
```
```bash
brew install node
```
```bash
brew install python
```
```bash
brew install wget
```
```bash
brew install gh        # GitHub CLI — manage repos from terminal
```
```bash
gh auth login          # authenticate gh with your GitHub account (browser flow)
```
```bash
brew install tree      # visualize directory structure
```

---

## 3. Install GUI Apps (Casks)

```bash
brew install --cask rectangle    # window snapping (macOS lacks this natively)
```
```bash
brew install --cask raycast      # better Spotlight: launcher + clipboard history
```
```bash
brew install --cask bitwarden    # free, open-source password manager
```

> **Web-first philosophy:** Notion, Slack, Figma etc. work fine in Chrome — skip native apps until you feel the need.

---

## 4. System Monitoring

Install a better process viewer:

```bash
brew install htop    # interactive, better than top
```
```bash
brew install btop    # even prettier — shows CPU, memory, disk, and network
```

Quick native checks (no install needed — run each separately):

```bash
top -o mem           # sort processes by memory usage — press q to quit
```
```bash
vm_stat              # raw virtual memory stats
```
```bash
memory_pressure      # simple health check: outputs good / warning / critical
```

---

## 5. Periodic Cleanup

Run these occasionally (e.g. monthly) to keep things tidy:

```bash
brew cleanup         # removes old versions of installed packages
```
```bash
brew autoremove      # removes unused dependencies
```
```bash
brew upgrade         # updates all installed packages
```

> 💡 Run each command on its own line — don't paste them together.

---

## 6. Privacy & Security

### macOS System Settings (no installs needed)

| Setting | Where |
|---|---|
| Turn on **Firewall** | System Settings → Privacy & Security → Firewall |
| Enable **FileVault** (full-disk encryption) | System Settings → Privacy & Security → FileVault |
| Restrict **AirDrop** | System Settings → General → AirDrop → Contacts Only (or Off) |
| Disable **Analytics** | System Settings → Privacy → Analytics → turn off |

### Chrome Settings

- `chrome://settings/cookies` → Block third-party cookies
- `chrome://settings/privacy` → Enable Enhanced Protection
- Install **[uBlock Origin](https://chrome.google.com/webstore/detail/ublock-origin/)** extension — best-in-class tracker/ad blocker

### Optional: Outbound Firewall

```bash
brew install --cask lulu    # free, open-source — prompts you when any app phones home
```

> Paid alternative: **Little Snitch** (~$45 one-time) for more granular control.

---

## 7. App Stack (Minimal)

| App | Purpose | Install |
|---|---|---|
| **Chrome** | Browser | [google.com/chrome](https://www.google.com/chrome) |
| **Claude** | AI assistant | [claude.ai](https://claude.ai) or App Store |
| **Rectangle** | Window management | `brew install --cask rectangle` |
| **Raycast** | Launcher + clipboard | `brew install --cask raycast` |
| **Bitwarden** | Password manager | `brew install --cask bitwarden` |
| **JetBrains IDE** | Dev (when edu license renewed) | [jetbrains.com](https://www.jetbrains.com) |

---

## Tips

- **Run commands one at a time** — never paste multi-line blocks with `#` comments directly into Terminal
- `#` comments in shell scripts are fine in `.sh` files, but pasting them into an interactive terminal causes errors
- Keep this README updated as your stack evolves

---

*Last updated: April 2026*
