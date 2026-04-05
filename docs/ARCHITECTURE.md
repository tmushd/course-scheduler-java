# Architecture

## High-level flow
1. `MainFrame` handles UI events and renders tables/status text.
2. Query classes (`SemesterQueries`, `CourseQueries`, `ClassQueries`, `StudentQueries`, `ScheduleQueries`, `MultiTableQueries`) encapsulate SQL operations.
3. Entry classes (`StudentEntry`, `CourseEntry`, `ClassEntry`, `ScheduleEntry`, `ClassDescription`) carry data between UI and query layers.
4. `DBConnection` provides a singleton JDBC connection.

## Module map
- `MainFrame.java` — all Swing views, event handlers, and workflow orchestration.
- `DBConnection.java` — Derby JDBC connection configuration.
- `*Queries.java` — CRUD and lookup methods for specific tables.
- `MultiTableQueries.java` — joined queries and filtered schedule views.
- `*Entry.java`, `ClassDescription.java` — data containers.

## Data model
The app uses one schema (`JAVA`) with five core tables.

| Table | Purpose |
|---|---|
| `semester` | list of active semester names |
| `course` | global course catalog |
| `class` | semester-specific offered courses + seat limits |
| `student` | student directory |
| `schedule` | enrollment records with status (`s` scheduled / `w` waitlisted) |

## Enrollment lifecycle
- User picks student + class.
- App compares class seat capacity with current scheduled count.
- If seats remain, status is `s`; otherwise status is `w`.
- Dropping a student/class promotes earliest waitlisted student (by timestamp) to `s`.

## Design notes
- Query classes use prepared statements for parameterized SQL.
- Waitlist behavior is implemented using status flag + insertion timestamp.
- UI is functional and data-driven, but currently monolithic in one large frame class.
