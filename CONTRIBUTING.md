# Contributing

Thanks for checking out Course Scheduler.

## Local development flow
1. Read [`docs/SETUP.md`](docs/SETUP.md).
2. Start Derby server and initialize schema.
3. Open `CourseSchedulerVayunandanreddyPannalaVFP5175` in NetBeans or build via Ant.
4. Validate core workflows manually:
   - Add semester/course/class/student
   - Schedule and waitlist behavior
   - Drop student/class and verify promotions
5. Run local compile check:
   - `./scripts/compile-app.sh`

## Pull request checklist
- Keep changes focused and easy to review.
- Update docs when setup, behavior, or architecture changes.
- Preserve existing naming/style in Java files.
- Include clear testing notes in PR description.
- Ensure GitHub Actions compile workflow stays green.

## Suggested areas for contribution
- UI modernization and accessibility improvements.
- Error handling and validation around duplicate/invalid input.
- Unit/integration test coverage for query classes.
- Better packaging and one-command local bootstrap.
