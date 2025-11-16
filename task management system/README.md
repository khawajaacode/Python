# Task Management System

A lightweight, queue-based task management system with a command-line interface built in Python.

## Features

- **Add Tasks** - Create new tasks with name, due date, and description
- **View Tasks** - Display all active tasks in queue order
- **Mark Complete** - Mark tasks as done and archive them
- **Peek Queue** - View the next task in the queue
- **Persistent Storage** - Tasks saved to files for data persistence
- **Logging** - Action and performance monitoring with decorators

## Project Structure

```
task management system/
├── cli.py              # Command-line interface
├── task.py             # TaskManager class with core logic
├── decorators.py       # Logging and timing decorators
├── queue.txt           # Active tasks storage
├── completed_tasks.txt # Archive of completed tasks
└── task_manager.log    # Activity and performance logs
```

## Components

### `task.py`
Core task management class with the following methods:

| Method | Description |
|--------|-------------|
| `__init__(filename)` | Initialize manager and load existing tasks |
| `add_task(name, due_date, description)` | Add a new task to queue |
| `view_tasks()` | Display all active tasks |
| `mark_complete(task_index)` | Mark task as complete and archive |
| `view_next_queue_task()` | Peek at the next task without removing |
| `save_tasks_to_file()` | Persist tasks to `queue.txt` |
| `save_completed_task(task)` | Archive completed task to `completed_tasks.txt` |

### `cli.py`
Menu-driven command-line interface with options:

1. **Add Task** - Create a new task
2. **View Tasks** - List all active tasks
3. **Mark Task Complete** - Complete and archive a task
4. **View Next Task** - See the next queued task
5. **Exit** - Close the application

### `decorators.py`
Utility decorators for monitoring and debugging:

- **`@log_action`** - Logs function calls with arguments to `task_manager.log`
- **`@timer`** - Measures and logs function execution time

## Task Format

Each task contains:
- `name` - Task title/name
- `due_date` - Deadline in YYYY-MM-DD format
- `completed` - Boolean completion status
- `description` - Detailed task information

## Data Persistence

### queue.txt
Stores active tasks in CSV format:
```
task_name,due_date,description
```

### completed_tasks.txt
Archives completed tasks with completion status

### task_manager.log
Records all actions and execution times for debugging and monitoring

## Getting Started

### Prerequisites
- Python 3.x

### Installation
1. Clone or download the project
2. Navigate to the project directory:
   ```bash
   cd "task management system"
   ```

### Usage
Run the application:
```bash
python cli.py
```

Follow the interactive menu to:
- Add new tasks
- View your task queue
- Mark tasks as complete
- Exit when done

## Example Workflow

```
1. Select "Add Task"
2. Enter task name: "Complete project report"
3. Enter due date: "2025-11-20"
4. Enter description: "Finish Q4 performance report"

5. Select "View Tasks" to see all tasks

6. Select "View Next Task" to see priority task

7. Select "Mark Task Complete" to finish a task
```

## File Output Examples

**queue.txt:**
```
Complete project report,2025-11-20,Finish Q4 performance report,False
Update documentation,2025-11-18,Add API docs,False
```

**task_manager.log:**
```
[2025-11-16 10:30:45] add_task called with args: ('Complete project report', '2025-11-20', 'Finish Q4 performance report')
[2025-11-16 10:30:46] add_task executed in 0.0234s
```

## Notes

- Tasks are processed in FIFO (First-In-First-Out) queue order
- Completed tasks are moved to `completed_tasks.txt` for record-keeping
- All operations are logged for auditability and debugging
- Execution times are tracked to monitor performance

## License

This project is part of the Python repository maintained by khawajaacode.
