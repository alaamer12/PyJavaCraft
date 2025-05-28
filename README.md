# 🚀 PyJavaCraft: Jython Integration Learning Journey

**PyJavaCraft** is a collaborative learning project between a Python developer (Amr Muhamed) and a Java developer (his friend). The goal is to master **Jython** integration by building hybrid applications that increase in complexity level-by-level, from basic CLI tools to enterprise-level apps with design patterns, databases, and optimization.

---

## 📚 Table of Contents

* [Project Structure](#project-structure)
* [Learning Goals](#learning-goals)
* [Levels Overview](#levels-overview)
* [Tech Stack](#tech-stack)
* [Setup Instructions](#setup-instructions)
* [Contributing Guide](#contributing-guide)
* [License](#license)

---

## 🏗 Project Structure

```bash
PyJavaCraft/
├── level_1_console_todo/         # Basic CLI integration
├── level_2_file_ui/              # File I/O + JavaFX UI
├── level_3_notes_plugins/        # Plugin-based architecture
├── level_4_sdk_template/         # SDK & plugin system
├── level_5_finance_tracker/      # MVC, DB, optimized logic
├── shared_docs/                  # Diagrams, decisions, architecture
│   └── architecture.md
└── meta/                         # Progress tracking, collaboration notes
    └── progress_tracker.md
```

---

## 🎯 Learning Goals

Each level teaches core principles of hybrid development:

* ✅ Seamlessly calling Java classes from Python using Jython
* ✅ Reversing roles: Java using Python logic
* ✅ Creating pluggable modules and SDKs
* ✅ Understanding MVC and design patterns in hybrid codebases
* ✅ Optimizing critical logic using Python (NumPy, etc.)
* ✅ Using JavaFX UI with Python-based behaviors

---

## 🧩 Levels Overview

### 🔹 Level 1 – Console-Based Todo App

* Learn basic Java↔Python calls
* Java: models and logic
* Python: CLI and interaction

### 🔹 Level 2 – File I/O + GUI

* JavaFX UI for task management
* File-based data persistence
* Python: filtering, validation logic

### 🔹 Level 3 – Notes App + Plugins

* Java: core app + plugin manager
* Python: multiple independent plugins (tagger, summarizer)

### 🔹 Level 4 – SDK Template

* Java SDK for hybrid development
* Python plugin lifecycle system
* Reusable template + guides

### 🔹 Level 5 – Finance Tracker (Expert+)

* Full MVC architecture
* PostgreSQL/SQLite integration (via JDBC)
* Optimized Python calculations (NumPy)
* Advanced reporting and charts

---

## 🛠 Tech Stack

### 🐍 Python:

* Python 3.x (logic, analytics, reports)
* NumPy, pandas (Level 5)

### ☕ Java:

* Java 11+
* JavaFX (UI)
* JDBC (DB access)

### 🔀 Integration:

* [Jython 2.7.3+](https://www.jython.org/)
* Java-to-Python using `PythonInterpreter`

### 🗃 Database (Level 5):

* SQLite or PostgreSQL
* SQL schema + ORM-like access

---

## ⚙️ Setup Instructions

### Prerequisites:

* Java JDK 11+
* Python 3.x
* Jython (install via jar or system-wide)

### Install Jython:

```bash
# Download and install
wget https://repo1.maven.org/maven2/org/python/jython-standalone/2.7.3/jython-standalone-2.7.3.jar

# Run with Java
java -jar jython-standalone-2.7.3.jar
```

### Running a Level

```bash
cd level_1_console_todo/
# Compile and run Java code
javac *.java
# Run Python integration using Jython
java -cp jython-standalone-2.7.3.jar:. Main
```

> Each level has its own `README.md` with level-specific instructions.

---

## 🤝 Contributing Guide

This is a two-person, synchronized project. All code is reviewed mutually.

**Workflow:**

* Branch per level: `level/1-todo`, `level/5-finance`, etc.
* PRs reviewed and merged only when both parties approve
* Commit messages follow conventional commits format

---

## 📜 License

MIT License © Amr Muhamed & Collaborator

---

## 🧠 Stretch Ideas (Optional Future Levels)

* Machine learning forecasting in Python
* Hybrid cloud sync app with REST backend
* Web-based GUI using Java Spring + Flask

> We believe this journey will make us better architects, not just better coders. 💡
