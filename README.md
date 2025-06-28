# 🧰 cli-helpers

A collection of simple, effective command-line utilities and scripts I use to automate everyday dev tasks — from Git hygiene to workflow shortcuts. Mostly Bash, with a sprinkle of nerd magic.

> ✨ Built by [tgenericx](https://github.com/tgenericx)

---

## 📜 Available Scripts

### `tag-undo`

🗑️ Undo (delete) the most recent Git tag — both locally and remotely.

```bash
tag-undo
````

#### 🔧 Features:

* Checks for Git repo
* Prompts before deleting
* Works with local + remote tags
* Safe by default

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
└── README.md
```

---

## 🛠️ Setup

1. Clone the repo:

```bash
git clone https://github.com/tgenericx/cli-helpers.git
```

2. Add scripts to your `$PATH` (optional):

```bash
chmod +x ./cli-helpers/*
sudo ln -s $(pwd)/cli-helpers/tag-undo /usr/local/bin/tag-undo
```

3. Use anywhere:

```bash
tag-undo
```

---

## 🧠 Philosophy

Tiny tools. Zero dependencies. Unix-style. Make the terminal work *for* you.

---

## 📌 License

MIT – use, fork, modify, no stress.
