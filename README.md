# 🧰 cli-helpers

A collection of simple, effective command-line utilities and scripts I use to automate everyday dev tasks — from Git hygiene to workflow shortcuts. Mostly Bash, with a sprinkle of nerd magic.

> ✨ Built by [tgenericx](https://github.com/tgenericx)

---

## ⚡ Quick Install

> 📦 Interactive installer (lets you choose a script):

```bash
curl -fsSL https://raw.githubusercontent.com/tgenericx/cli-helpers/main/install | bash
````

> 🧪 Install **all available** tools at once:

```bash
curl -fsSL https://raw.githubusercontent.com/tgenericx/cli-helpers/main/install | bash -s -- --all
```

> 🧼 Automatically handles `sudo` or not (Termux-friendly)

---

## 📜 Available Scripts

Scripts listed in [`utils.txt`](https://chatgpt.com/c/utils.txt):

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
├── tag-undo         # Bash script to undo latest Git tag
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

## 🛠 Manual Setup (if you don’t want to use the installer)

```bash
git clone https://github.com/tgenericx/cli-helpers.git
cd cli-helpers
chmod +x tag-undo
sudo mv tag-undo /usr/local/bin/tag-undo  # Optional: skip sudo if root or on Termux
```

---

## 🧼 Uninstall

```bash
sudo rm /usr/local/bin/tag-undo
```

---

## 📌 License

MIT – use, fork, modify, no stress.
