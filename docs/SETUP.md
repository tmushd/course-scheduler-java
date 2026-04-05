# Setup Guide

This guide covers local setup from zero to running UI.

## Prerequisites
- Java JDK 11 or newer
- Apache Derby (network server + tools + client JAR)
- Optional: Apache Ant (for CLI builds)
- Optional: NetBeans (recommended for easiest run/debug)

## 1) Clone and enter project
```bash
git clone https://github.com/tmushd/CourseScheduler.git
cd CourseScheduler
```

## 2) Configure Derby location
Set `DERBY_HOME` to your Derby install directory:

```bash
export DERBY_HOME=/absolute/path/to/db-derby-10.15.2.0-bin
```

## 3) Start Derby network server
```bash
./scripts/start-derby-server.sh
```

Default server target is `localhost:1527`.

## 4) Initialize schema (fresh database path)
```bash
./scripts/create-schema.sh
```

Optional demo seed data:
```bash
./scripts/load-seed-data.sh
```

## 5) Run the app

### Option A: NetBeans (recommended)
1. Open `CourseSchedulerVayunandanreddyPannalaVFP5175` as a NetBeans project.
2. Ensure Derby client library resolves in project classpath.
3. Run `MainFrame`.

### Option B: Command line (Ant)
```bash
ant -Dlibs.JAVADB_DRIVER_LABEL.classpath="$DERBY_HOME/lib/derbyclient.jar" \
  -f CourseSchedulerVayunandanreddyPannalaVFP5175/build.xml clean jar

java -cp "CourseSchedulerVayunandanreddyPannalaVFP5175/dist/CourseSchedulerVayunandanreddyPannalaVFP5175.jar:$DERBY_HOME/lib/derbyclient.jar" MainFrame
```

For Windows, replace `:` with `;` in the Java classpath.

### Option C: Command line helper script (fastest)
```bash
./scripts/run-app.sh
```

This script compiles sources into `build-cli` and launches `MainFrame`.
If `DERBY_HOME/lib/derbyclient.jar` is present, it is automatically added to runtime classpath.

## 6) Database connection environment variables
The app supports overrides through env vars:

- `COURSE_SCHEDULER_DB_URL`
- `COURSE_SCHEDULER_DB_HOST`
- `COURSE_SCHEDULER_DB_PORT`
- `COURSE_SCHEDULER_DB_NAME`
- `COURSE_SCHEDULER_DB_USER`
- `COURSE_SCHEDULER_DB_PASSWORD`

Example:
```bash
export COURSE_SCHEDULER_DB_HOST=127.0.0.1
export COURSE_SCHEDULER_DB_PORT=1527
export COURSE_SCHEDULER_DB_NAME=CourseSchedulerDBVayunandanreddyPannalaVFP5175
export COURSE_SCHEDULER_DB_USER=java
export COURSE_SCHEDULER_DB_PASSWORD=java
```

## Troubleshooting
- `command not found: ant` → install Ant or run through NetBeans.
- Derby connection errors → confirm server is running and host/port match env vars.
- Duplicate key SQL errors → expected if re-running seed on an existing database.
