# FAQ

## Why Derby and Swing?
This project began as a desktop academic scheduling app and is intentionally kept as a Java Swing + Derby stack to demonstrate core Java engineering, SQL workflow logic, and local-first setup.

## Does this support waitlisting?
Yes. When class capacity is reached, enrollments are recorded with waitlist status and promoted by earliest timestamp when a seat opens.

## Can I run this without NetBeans?
Yes. Use `./scripts/run-app.sh` or compile via Ant as documented in [`docs/SETUP.md`](SETUP.md).

## What should be improved next?
Use the staged plan in [`docs/ROADMAP.md`](ROADMAP.md): automated tests, UI modularization, and eventual service/API architecture.
