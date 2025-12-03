# Advanced Python Projects Repository

A collection of Python applications demonstrating various development techniques and best practices, including task management systems and web development with Flask.

## 📋 Overview

This repository contains multiple Python projects showcasing different programming paradigms and technologies:

| Project | Description | Tech Stack |
|---------|-------------|-----------|
| **Intelligent Blog Application** | A Flask-based web application for creating and managing blog posts | Flask, HTML, JavaScript |
| **Task Management System** | A queue-based CLI application for managing tasks with persistence | Python, Collections, Decorators |
| **Symptom Diagnosis Chatbot** | An AI-powered notebook that provides preliminary medical diagnoses based on user-reported symptoms. |Python, spaCy, Jupyter Notebook |

---

## 🎓 Certification

![Microsoft Advanced Python Development Certificate](./Coursera%20BNCIC3OK0ITD.jpg)

- **Verification:** [https://coursera.org/verify/BNCIC3OK0ITD](https://coursera.org/verify/BNCIC3OK0ITD)

---

## 📁 Project Structure

```
Python/
├── README.md                          # This file
├── Coursera BNCIC3OK0ITD.jpg         # Course completion certificate
│
├── Intelligent blog application/      # Flask web application
│   ├── app.py                        # Flask application entry point
│   ├── templates/
│   │   └── index.html               # Frontend HTML template
│   ├── static/
│   │   └── script.js                # Frontend JavaScript
│   └── tests/
│       ├── conftest.py              # Pytest configuration
│       └── test_app.py              # Unit tests
│
└── task management system/            # CLI task manager
    ├── README.md                      # Project-specific documentation
    ├── cli.py                         # Command-line interface
    ├── task.py                        # Core TaskManager class
    ├── decorators.py                  # Logging and timing decorators
    ├── queue.txt                      # Active tasks storage
    ├── completed_tasks.txt            # Completed tasks archive
    └── task_manager.log               # Activity and performance logs
```

---

## 🚀 Projects

### 1. Intelligent Blog Application

A full-stack web application built with Flask for managing blog posts.

#### Features
- ✅ Create new blog posts with title and content
- ✅ Retrieve all posts via REST API
- ✅ Real-time UI updates with JavaScript
- ✅ Input validation and error handling
- ✅ Unit test coverage with pytest

#### Technology Stack
- **Backend:** Flask (Python web framework)
- **Frontend:** HTML5, JavaScript
- **Testing:** pytest, conftest

#### Quick Start

```bash
cd "Intelligent blog application"
python app.py
```

Then open your browser and navigate to `http://localhost:5000`

#### API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/` | Render blog interface |
| GET | `/posts` | Retrieve all posts |
| POST | `/posts` | Create a new post |

#### Request/Response Example

**Create Post:**
```bash
POST /posts
Content-Type: application/json

{
  "title": "My First Post",
  "content": "This is my blog content"
}
```

**Response:**
```json
{
  "id": 1,
  "title": "My First Post",
  "content": "This is my blog content"
}
```

#### Running Tests

```bash
cd "Intelligent blog application"
pytest tests/
```

---

### 2. Task Management System

A queue-based task management system with a command-line interface, persistent storage, and comprehensive logging.

#### Features
- ✅ Add tasks with name, due date, and description
- ✅ View all active tasks in queue order
- ✅ Mark tasks as complete and archive them
- ✅ Peek at the next task without removing it
- ✅ Persistent storage with file operations
- ✅ Action logging and performance monitoring
- ✅ FIFO (First-In-First-Out) queue processing

#### Technology Stack
- **Data Structure:** Collections.deque for efficient queue operations
- **Persistence:** File-based storage (CSV format)
- **Monitoring:** Custom decorators for logging and timing
- **Interface:** Command-line menu system

#### Quick Start

```bash
cd "task management system"
python cli.py
```

#### Menu Options

1. **Add Task** - Create a new task with name, due date, and description
2. **View Tasks** - Display all active tasks
3. **Mark Task Complete** - Complete a task and archive it
4. **View Next Task** - Peek at the next task in queue
5. **Exit** - Exit the application

#### Data Files

| File | Purpose |
|------|---------|
| `queue.txt` | Stores active tasks in CSV format |
| `completed_tasks.txt` | Archives completed tasks |
| `task_manager.log` | Records actions and execution times |

#### Task Format

```csv
task_name,due_date,completed,description
```

Example:
```csv
Complete project report,2025-11-20,False,Finish Q4 performance report
Update documentation,2025-11-18,False,Add API docs
```

#### Example Workflow

```
1. Add Task
   Name: "Complete project report"
   Due Date: "2025-11-20"
   Description: "Finish Q4 performance report"

2. View Tasks
   [Display all active tasks]

3. View Next Task
   [Peek at the priority task]

4. Mark Task Complete
   [Archive the completed task]
```

#### Core Classes & Methods

**TaskManager Class:**
- `__init__(filename)` - Initialize and load existing tasks
- `add_task(name, due_date, description)` - Add new task
- `view_tasks()` - Display all tasks
- `mark_complete(task_index)` - Complete and archive task
- `view_next_queue_task()` - Peek at next task
- `save_tasks_to_file()` - Persist tasks
- `save_completed_task(task)` - Archive completed task

**Decorators:**
- `@log_action` - Logs function calls and arguments
- `@timer` - Measures and logs execution time

---

## 📊 Comparison

| Aspect | Blog Application | Task Manager |
|--------|------------------|--------------|
| **Type** | Web Application | CLI Application |
| **Interface** | Web UI (Browser) | Command-line Menu |
| **Data Storage** | In-memory (posts list) | File-based (queue.txt) |
| **Framework** | Flask | Python Standard Library |
| **Data Structure** | List | Collections.deque |
| **Testing** | pytest framework | Manual CLI testing |
| **Use Case** | Publishing platform | Personal productivity |

---

## 🛠️ Installation & Setup

### Prerequisites
- Python 3.x
- pip (Python package manager)

### System-wide Setup

1. **Clone the repository:**
   ```bash
   git clone <repository-url>
   cd "Python Repo/Python"
   ```

2. **Install dependencies (for Flask app):**
   ```bash
   pip install flask pytest
   ```

3. **Run individual projects:**
   ```bash
   # Blog Application
   cd "Intelligent blog application"
   python app.py

   # Task Manager
   cd "task management system"
   python cli.py
   ```

---

## 📝 Development Guidelines

### Code Organization
- Each project is self-contained in its own directory
- Clear separation of concerns (UI, logic, data)
- Modular function and class design
- Comprehensive docstrings and comments

### Testing
- Blog app includes pytest test suite
- Task manager has manual CLI testing support
- All functions include type hints and documentation

### Logging & Monitoring
- Task manager includes action logging
- Performance timing available via `@timer` decorator
- Audit trail for all task operations

---

## 🎯 Learning Outcomes

This repository demonstrates:
- ✅ Flask web framework and REST API design
- ✅ Queue data structures and FIFO processing
- ✅ File I/O and data persistence
- ✅ Python decorators for cross-cutting concerns
- ✅ Command-line interface design
- ✅ Unit testing with pytest
- ✅ HTML/CSS/JavaScript frontend development
- ✅ Data validation and error handling

---

## 📖 Documentation

Each project includes its own detailed documentation:
- `task management system/README.md` - Task manager documentation
- Inline code comments and docstrings throughout

---

## 🔗 Repository Information

- **Repository Name:** Python
- **Owner:** khawajaacode
- **Branch:** main
- **Last Updated:** November 20, 2025

---

## 📄 License

This repository is part of the Python learning journey and demonstrates various Python development techniques.


For questions or issues with any project, review the inline documentation, project-specific READMEs, or test files for usage examples
