# 📘 LEVEL 3 GUIDE – Multi-Module App with Realtime Sync & CLI

## 🎯 Goal

Build a task management system with **Java GUI (JavaFX)** and **Python CLI interface**, both sharing the same task data. Sync changes between both interfaces in real-time (or simulate it via polling/file-watching).

---

## 👥 Responsibilities

### 🧠 Java Developer (Your Friend)

* Extend JavaFX GUI to support:

  * Task editing
  * Task priority
  * Real-time reload (by detecting file or state changes)
* Package GUI into a self-contained module (`gui/`)

### 🐍 Python Developer (You)

* Implement a **CLI interface** to list/add/edit/complete tasks
* Read/write to the same JSON file used by Java GUI
* Use Python’s `watchdog` or polling to detect file changes and reload UI
* Package CLI into a standalone module (`cli/`)

---

## 🗂 Directory Structure (Suggested)

```bash
level_3_multimodule/
├── gui/
│   ├── Task.java
│   ├── TaskManager.java
│   └── TaskApp.java
├── cli/
│   ├── cli.py               # CLI entry
│   ├── sync.py              # JSON sync manager
│   └── utils.py             # Print helpers
├── shared/
│   ├── tasks.json           # Shared storage
│   └── schema.py            # Optional: for consistency
├── LEVEL3_GUIDE.md
```

---

## 🔁 Integration Overview

1. Both JavaFX and Python CLI interact with the shared JSON
2. Each side checks for file changes before each read
3. Avoid race conditions (e.g., lock file while writing)

---

## 🧪 Sample CLI Output

```bash
$ python cli.py list
[1] ✖ Buy milk
[2] ✔ Submit report

$ python cli.py add "Walk dog"
✅ Added: Walk dog
```

---

## 🐍 Python CLI Commands

* `add <desc>` – add task
* `done <id>` – mark as done
* `list` – show all tasks
* `watch` – auto-refresh display when file changes (optional)

---

## 📦 JavaFX Enhancements

* Add priority field (low/medium/high)
* Add file-watch functionality (via thread or timer)

---

## ✅ Success Criteria

* Both GUI and CLI can edit and sync tasks
* Consistent task state across both interfaces
* No data loss or overwrite issues

---

## 🧠 Tips

* Use file-based locking or polling strategy
* Normalize task structure across modules
* Consider using an event log model (optional advanced feature)

---

## 🚦 Ready for Level 4 When...

* GUI and CLI work with the same data
* Real-time or manual syncing works without breaking either interface
* Your Python CLI feels like a professional terminal tool
