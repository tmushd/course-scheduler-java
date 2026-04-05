# Demo Script (5–7 minutes)

Use this script in interviews, portfolio videos, or recruiter walkthroughs.

## 1) Project intro (30 seconds)
- “This is a Java Swing course scheduler backed by Derby.”
- “It supports admin workflows, student scheduling, and waitlist promotion.”
- “I improved reliability, setup automation, and documentation to make it production-style.”

## 2) Environment startup (60 seconds)
```bash
export DERBY_HOME=/absolute/path/to/db-derby-10.15.2.0-bin
./scripts/start-derby-server.sh
./scripts/create-schema.sh
./scripts/load-seed-data.sh
./scripts/run-app.sh
```

## 3) Admin workflow (2 minutes)
1. Add a new semester.
2. Add a course to catalog.
3. Add a class section with limited seats.
4. Add a new student.

Callout:
- Show status labels and data-refresh behavior in combo boxes.

## 4) Student workflow (2 minutes)
1. Display available classes.
2. Schedule students into the same class until seats are full.
3. Schedule one more student and show waitlist status.
4. Display class roster to show scheduled vs waitlisted tables.

Callout:
- Explain seat-limit logic and automatic `scheduled`/`waitlisted` status assignment.

## 5) Drop flow and promotion logic (1 minute)
1. Drop one enrolled student from class.
2. Show that earliest waitlisted student is auto-promoted.

Callout:
- Mention timestamp ordering and deterministic waitlist promotion.

## 6) Engineering closeout (30 seconds)
- “The repo now has setup scripts, schema/seed SQL, CI compile checks, and architecture docs.”
- “I can extend this into a service-based architecture or add automated tests next.”
