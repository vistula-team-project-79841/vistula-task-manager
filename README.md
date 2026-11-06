# Task Manager

A browser-based task manager for the Vistula University team assignment. The application uses the Supabase REST API and supports public create, read, update and delete operations on the `tasks` table.

## Student

- Student ID: `79841`
- GitHub repository: https://github.com/vistula-team-project-79841/vistula-task-manager
- Live application: https://vistula-team-project-79841.github.io/vistula-task-manager/
- Supabase project: https://supabase.com/dashboard/project/vuqcmmgozrcangvfeilb

## Files

- `index.html` contains the responsive user interface.
- `app.js` calls the Supabase REST API and implements CRUD operations.
- `config.json` contains the project URL, publishable key and required `tasks` table name.
- `contribution.html` displays the contributor page added by student `79822` through a Pull Request.
- `contribution.json` contains the contributor student ID supplied by student `79822`.
- `README.md` documents the project and collaboration workflow.

## Data model

The public `tasks` table contains:

- `id` as an auto-generated `int8` primary key
- `title` as `text`
- `description` as `text`
- `completed` as `bool`

Row Level Security is enabled. Separate `anon` policies allow `SELECT`, `INSERT`, `UPDATE` and `DELETE` for this coursework demo. No secret key or legacy `service_role` key is stored in this repository.

## REST API

The application sends requests to:

```text
GET    /rest/v1/tasks?select=*
POST   /rest/v1/tasks
PATCH  /rest/v1/tasks?id=eq.<id>
DELETE /rest/v1/tasks?id=eq.<id>
```

Every request uses the publishable key from `config.json` in the `apikey` header. Supabase RLS policies remain the actual authorization boundary.

## Team collaboration

The collaboration is between student `79841` and student `79822`. Each student keeps a separate public repository and contributes the required `contribution.html` and `contribution.json` files through a Pull Request.

- Incoming contribution from student `79822`: https://github.com/vistula-team-project-79841/vistula-task-manager/pull/1
- Outgoing contribution from student `79841`: https://github.com/vistula-team-project-79822/vistula-task-manager/pull/1
- Live contributor page: https://vistula-team-project-79841.github.io/vistula-task-manager/contribution.html
- Live contributor JSON: https://vistula-team-project-79841.github.io/vistula-task-manager/contribution.json

The contributor files in this repository were authored by student `79822` and merged through the incoming Pull Request. They were not created directly by the repository owner.

## Local use

Serve the folder through a local web server because browsers can block `fetch()` from `file://` pages:

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000.
