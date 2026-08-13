# Day 08 - Process Management

## Overview

A process is a running instance of a program. Linux provides commands to view, monitor, control, and change the priority of running processes.

---

# Viewing Processes

## ps

Shows processes running in the current shell session.

```bash
ps
```

---

## ps aux

Shows detailed information about all running processes.

```bash
ps aux
```

Important columns include:

- `USER` → User who owns the process
- `PID` → Process ID
- `%CPU` → CPU usage
- `%MEM` → Memory usage
- `STAT` → Process state
- `COMMAND` → Command that started the process

---

## top

Provides a real-time view of running processes and system resource usage.

```bash
top
```

Useful keys:

- `q` → Quit
- `k` → Kill a process
- `P` → Sort by CPU usage
- `M` → Sort by memory usage

---

## htop

An interactive and more user-friendly alternative to `top`.

```bash
htop
```

It may need to be installed first:

```bash
sudo apt install htop
```

---

## pgrep

Finds the PID of a process using its name.

```bash
pgrep <name>
```

Example:

```bash
pgrep nginx
```

---

# Controlling Processes

## kill

Sends a signal to a process using its PID.

```bash
kill <PID>
```

By default, `kill` sends `SIGTERM`, which requests the process to terminate gracefully.

---

## kill -9

Forcefully terminates a process using `SIGKILL`.

```bash
kill -9 <PID>
```

Use it when a process does not respond to a normal `kill`.

---

## killall

Terminates processes by their name.

```bash
killall <name>
```

Example:

```bash
killall firefox
```

Be careful because it can terminate multiple processes with the same name.

---

# Process Priority

Linux assigns a priority to processes using a value called **niceness**.

- Lower nice value → Higher priority
- Higher nice value → Lower priority
- Normal nice value → `0`

---

## nice

Starts a new process with a specified nice value.

```bash
nice -n 10 <command>
```

Example:

```bash
nice -n 10 ./script.sh
```

---

## renice

Changes the nice value of an already running process.

```bash
renice 10 -p <PID>
```

Example:

```bash
renice 10 -p 1234
```

---

# Important Points

- `ps` → View processes.
- `ps aux` → View all processes with detailed information.
- `top` → Monitor processes in real time.
- `htop` → Interactive process monitoring.
- `pgrep` → Find a process PID by name.
- `kill` → Gracefully request a process to terminate.
- `kill -9` → Forcefully terminate a process.
- `killall` → Terminate processes by name.
- `nice` → Set priority when starting a process.
- `renice` → Change priority of an existing process.
- Every running process has a unique **PID (Process ID)**.
