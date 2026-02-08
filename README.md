# 🧰 cli-helpers

A collection of simple, effective command-line utilities and scripts I use to automate everyday dev tasks — from Git hygiene to workflow shortcuts. Mostly Bash, with a sprinkle of nerd magic.

> ✨ Built by [tgenericx](https://github.com/tgenericx)

---

## ⚡ Quick Install

> 📦 Interactive installer (lets you choose a script):

```bash
bash <(curl -fsSL https://raw.githubusercontent.com/tgenericx/cli-helpers/main/install)
```

> 🧪 Install **all available** tools at once:

```bash
curl -fsSL https://raw.githubusercontent.com/tgenericx/cli-helpers/main/install | bash -s -- --all
```

> 🧼 Automatically handles `sudo` or not (Termux-friendly)

---

## 🛠️ Available Tools

### `gu` (git update)

🔄 Smart Git workflow automation — updates your feature branch with the latest changes from main/master (or any target branch).

```bash
gu [branch] [--merge] [--no-stash]
```

#### 🔧 Features:

- **Auto-detects target branch** from upstream or repository default
- **Safely stashes** uncommitted changes (restored after update)
- **Updates target branch** from remote (main/master/etc.)
- **Rebases your feature branch** onto the updated target
- **Returns to original branch** even if something fails
- **Conflict-friendly** with helpful recovery instructions

#### 💡 Example usage:

```bash
# On feature branch - auto-detects and updates from main
$ gu
📌 Current branch: feature/new-widget
📌 Target branch: main (from upstream: origin)
💾 Stashing uncommitted changes...
🔄 Switching to main...
📥 Fetching latest from origin...
🔄 Updating main...
🔄 Returning to feature/new-widget...
♻️ Updating feature branch from main...
📤 Applying stashed changes...
✅ Update complete!

# Specify a different target branch
$ gu develop

# Use merge instead of rebase
$ gu --merge

# Skip auto-stashing (if you've already committed)
$ gu --no-stash
```

#### 🎯 What it does:

1. Stashes your current work (unless `--no-stash`)
2. Switches to target branch (main/master/etc.)
3. Fetches and updates target from remote
4. Returns to your feature branch
5. Rebases (or merges with `--merge`) your branch onto updated target
6. Restores your stashed changes

---

### `tag-undo`

🗑️ Undo (delete) the most recent Git tag — both locally and remotely.

```bash
tag-undo
```

#### 🔧 Features:

- Detects if you're in a Git repo
- Prompts before deleting
- Removes tag locally and from remote
- Safe, interactive by default

#### 💡 Example usage:

```bash
$ git tag
v1.0.0
$ tag-undo
🗑️  Tag to delete: v1.0.0
Are you sure you want to delete this tag locally and remotely? (y/N): y
✅ Deleted tag 'v1.0.0' locally and remotely.
```

---

## 📁 File Structure

```
cli-helpers/
├── gu               # Smart git workflow automation
├── tag-undo         # Undo latest Git tag
├── utils.txt        # List of scripts used by the installer
├── install          # Universal install script (curl-compatible)
└── README.md
```

---

## 🧠 Philosophy

- Tiny tools with zero dependencies
- Simple Bash + POSIX style
- Cross-platform friendly (Termux, Linux, WSL, macOS)
- Designed to _just work_

---

## 🛠 Manual Setup (if you don't want to use the installer)

```bash
git clone https://github.com/tgenericx/cli-helpers.git
cd cli-helpers
chmod +x gu tag-undo
sudo mv gu tag-undo /usr/local/bin/  # Optional: skip sudo if root or on Termux
```

---

## 🧼 Uninstall

```bash
sudo rm /usr/local/bin/gu
sudo rm /usr/local/bin/tag-undo
```

---

## 📌 License

MIT – use, fork, modify, no stress.
