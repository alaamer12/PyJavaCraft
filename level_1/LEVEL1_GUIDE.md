# 📘 LEVEL 1 GUIDE – Console-Based Todo App

## 🎯 Goal

Create a simple CLI-based todo application using Java for logic and models, and Python (via Jython) for the interface and filtering.

---

## 👥 Responsibilities

### 🧠 Java Developer (Your Friend)

* Define the core `Task` class: `id`, `description`, `done`
* Implement `TaskManager` class with:

  * `addTask(String desc)`
  * `listTasks()`
  * `completeTask(int id)`

### 🐍 Python Developer (You)

* Build a Python CLI using `input()` and `print()`
* Use Jython to call `TaskManager` methods from Python
* Implement logic to filter/display tasks (e.g. only completed)

---

## 🗂 Directory Structure (Suggested)

```bash
level_1_console_todo/
├── Task.java
├── TaskManager.java
├── cli.py
├── run.sh  # Optional launcher script
└── LEVEL1_GUIDE.md
```

---

## 🔁 Integration Flow

1. Java compiles the `.class` files
2. Python script imports and instantiates `TaskManager`
3. Python handles user input and invokes Java logic

---

## 💡 Example Code

### Java - Task.java

```java
public class Task {
    public int id;
    public String description;
    public boolean done = false;

    public Task(int id, String description) {
        this.id = id;
        this.description = description;
    }

    public void complete() {
        this.done = true;
    }
}
```

### Java - TaskManager.java

```java
import java.util.*;

public class TaskManager {
    private List<Task> tasks = new ArrayList<>();
    private int nextId = 1;

    public void addTask(String description) {
        tasks.add(new Task(nextId++, description));
    }

    public List<Task> listTasks() {
        return tasks;
    }

    public void completeTask(int id) {
        for (Task t : tasks) {
            if (t.id == id) {
                t.complete();
            }
        }
    }
}
```

### Python - cli.py

```python
from java.util import ArrayList
from TaskManager import TaskManager

manager = TaskManager()

while True:
    cmd = input("[add/list/complete/exit]: ")
    if cmd == "add":
        desc = input("Enter task description: ")
        manager.addTask(desc)
    elif cmd == "list":
        tasks = manager.listTasks()
        for t in tasks:
            status = "✅" if t.done else "❌"
            print(f"{t.id}: {t.description} {status}")
    elif cmd == "complete":
        tid = int(input("Enter task ID to complete: "))
        manager.completeTask(tid)
    elif cmd == "exit":
        break
```

---

## ✅ Success Criteria

* CLI works interactively
* Python can call Java classes via Jython
* Data managed entirely by Java, but displayed via Python

---

## 🧪 Bonus Ideas

* Add task priority
* Sort tasks in Python before displaying
* Add file persistence using JSON or CSV

Ready to move to Level 2 after this is complete and stable. 🚦
