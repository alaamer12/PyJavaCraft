# 📘 LEVEL 4 GUIDE – Networked Multi-User System with Socket Communication

## 🎯 Goal

Evolve the task app into a **multi-user, network-based system**. Implement a **Java server** that manages all tasks and client connections. Clients can be:

* Python CLI (your part)
* JavaFX GUI (your friend's part)

All task interactions go through the network via **socket communication**.

---

## 👥 Responsibilities

### 🧠 Java Developer (Your Friend)

* Build a **Java server** that supports multiple clients

  * Accept commands: `ADD`, `DONE`, `LIST`, etc.
  * Store tasks in-memory or persistently
* Implement JavaFX client to connect to the server
* Ensure thread-safe client handling and communication

### 🐍 Python Developer (You)

* Build a **Python CLI client** that connects to the Java server via socket
* Send commands and receive responses from server
* Create reusable `client.py` module with:

  * `send_command(cmd: str) -> str`
  * Handle JSON or newline-based protocols

---

## 🗂 Directory Structure (Suggested)

```bash
level_4_networked/
├── server/
│   ├── Server.java
│   ├── TaskManager.java
│   └── ClientHandler.java
├── client_java/
│   ├── GUIClient.java
│   └── JavaFX UI
├── client_python/
│   ├── cli.py
│   └── client.py
├── protocol/
│   └── README.md        # Command structure and message format
├── LEVEL4_GUIDE.md
```

---

## 🔌 Protocol Example (Text-Based)

```
> ADD|Buy Milk
< OK|Task added

> DONE|2
< OK|Task marked as done

> LIST
< JSON|[{"id":1, "desc":"Buy Milk", "done":false}]
```

Or use JSON messages per line:

```json
{"command": "ADD", "description": "Buy Milk"}
```

---

## 🔁 Integration Overview

1. Server starts and listens on port (e.g., 5050)
2. Python CLI connects and sends command strings
3. Server responds with result or updated data
4. Java GUI client does the same

---

## ✅ Success Criteria

* Server can handle multiple clients (Java or Python)
* Clients send commands and receive updates
* Tasks are synchronized and managed centrally

---

## 🧠 Tips

* Use TCP sockets with a newline-based or JSON protocol
* Add message length headers if needed (advanced)
* Design a simple command schema
* Server should log commands per user/session

---

## 📦 Enhancements

* Add unique user/session ID (optional)
* Use threads or thread pool for handling clients
* Track commands per user

---

## 🚦 Ready for Level 5 When...

* Server manages all data
* Python and Java clients interact via network
* Protocol is robust and extendable
* Both clients work in sync with the server
