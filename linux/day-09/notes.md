# Day 09 - Background & Foreground Jobs

## Overview

Linux allows processes to run in the foreground or background. Background jobs are useful when you want a command to keep running while continuing to use the terminal.

---

# Foreground & Background

## Foreground

A foreground command occupies the terminal until it finishes.

```bash
sleep 100
```

The terminal remains occupied while the command is running.

---

## Background (`&`)

Adding `&` runs a command in the background.

```bash
sleep 100 &
```

The command runs in the background and the terminal becomes available for other commands.

---

# Managing Jobs

## jobs

Lists background and suspended jobs in the current shell.

```bash
jobs
```

Example:

```text
[1]+  Running    sleep 100 &
```

`[1]` is the job number.

---

## jobs -l

Displays background jobs along with their PIDs.

```bash
jobs -l
```

---

## Ctrl + Z

Suspends the currently running foreground process.

```bash
sleep 100
```

Press:

```text
Ctrl + Z
```

The process is paused and becomes a suspended job.

---

## bg

Resumes a suspended job in the background.

```bash
bg %1
```

Here `%1` refers to job number 1.

---

## fg

Brings a background or suspended job to the foreground.

```bash
fg %1
```

---

# nohup

`nohup` allows a command to continue running even after the terminal is closed or the user logs out.

```bash
nohup command &
```

Example:

```bash
nohup ./script.sh &
```

If output is not redirected, it is normally written to `nohup.out`.

---

# Job Management

## disown

Removes a job from the shell's job table.

```bash
disown %1
```

The shell no longer manages that job.

---

## disown -h

Prevents the shell from sending a hangup signal to the job when the shell exits.

```bash
disown -h %1
```

---

## wait

Waits for a background job to finish.

```bash
wait %1
```

Useful in shell scripts when another operation depends on a background job finishing.

---

# Job Number vs PID

A **job number** belongs to the current shell:

```text
%1
```

A **PID (Process ID)** identifies the actual running process:

```text
1234
```

For example:

```bash
fg %1
```

uses a **job number**, while:

```bash
kill 1234
```

uses a **PID**.

---

# Important Points

- Foreground jobs occupy the terminal.
- `&` runs a command in the background.
- `Ctrl + Z` suspends a foreground job.
- `bg` resumes a suspended job in the background.
- `fg` brings a job to the foreground.
- `jobs` lists background and suspended jobs.
- `jobs -l` also displays PIDs.
- `nohup` keeps a command running after logout.
- `disown` removes a job from shell management.
- `wait` waits for a background job to finish.
- `%1` represents job number 1, while a PID identifies the actual process.
