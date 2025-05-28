# 📘 LEVEL 2 GUIDE – GUI Task App with File I/O

## 🎯 Goal

Build a GUI-based task management app using **JavaFX** for the interface and **Python (Jython)** for validation and filtering logic. Introduce **file-based persistence** (e.g., save/load tasks as JSON).

---

## 👥 Responsibilities

### 🧠 Java Developer (Your Friend)

* Build the JavaFX GUI (buttons, list views, inputs)
* Implement the `Task` and `TaskManager` classes (reuse/extend from Level 1)
* Handle file operations:

  * `saveToFile(String filename)` (writes JSON)
  * `loadFromFile(String filename)` (reads JSON)

### 🐍 Python Developer (You)

* Implement filtering logic (e.g., show tasks by keyword or date)
* Validate inputs before sending to Java (`check_description_length(desc)`, etc.)
* Parse/filter loaded tasks for GUI presentation (e.g., sort by priority)

---

## 🗂 Directory Structure (Suggested)

```bash
level_2_file_ui/
├── Task.java
├── TaskManager.java
├── TaskApp.java               # JavaFX GUI
├── TaskIO.java                # File saving/loading (JSON)
├── filters.py                 # Python filtering logic
├── validators.py              # Input validation
├── demo_integration.py        # Python-Java bridge testing
└── LEVEL2_GUIDE.md
```

---

## 💡 Flow Overview

1. JavaFX initializes the UI
2. Events call Python logic for validation
3. Tasks are saved/loaded using file I/O
4. Filtered results shown in GUI (via Python logic)

---

## 🔁 Integration Flow

* Java uses `PythonInterpreter` to execute Python functions (validation, filtering)
* Python may access Java objects via `from java_package import ...`
* Shared `Task` structure ensures compatibility between both sides

---

## 🧪 JSON Format (for Task persistence)

```json
[
  { "id": 1, "description": "Buy milk", "done": false },
  { "id": 2, "description": "Submit report", "done": true }
]
```

---

## ✅ Success Criteria

* JavaFX UI runs with task listing, add, complete, and filter features
* Tasks are saved and restored from JSON files
* Python logic is invoked by Java for input validation and task filtering

---

## 📦 Suggested JavaFX Features

* Input form (description field + Add button)
* Task ListView (with checkbox or status column)
* Filter TextField (calls Python)
* Menu or button for `Save` and `Load`

---

## 🐍 Python Logic Sample – filters.py

```python
def keyword_filter(tasks, keyword):
    return [t for t in tasks if keyword.lower() in t.description.lower()]
```

## 🐍 Python Logic Sample – validators.py

```python
def is_valid_description(desc):
    return desc and len(desc.strip()) >= 3
```

---

## 🧠 Tips

* Use GSON or Jackson in Java to serialize/deserialize JSON
* Ensure Python has access to task data via Jython bridge
* Use method handles to call Python from Java: `interpreter.eval("...")`

---

## 🚦 Ready for Level 3 When...

* You can save/load tasks
* UI filters using Python logic
* Java and Python roles are well coordinated and no circular dependency exists
