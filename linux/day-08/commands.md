# Process & Job Management

## Viewing Processes

- `ps` : Show processes running in the current shell session.
- `ps aux` : Show all running processes system-wide with detailed information.
- `top` : Display running processes and resource usage in real time.
- `htop` : Interactive and user-friendly process viewer.
- `pgrep <name>` : Find process IDs (PIDs) matching a process name.

---

## Controlling Processes

- `kill <PID>` : Send a termination signal to a process by its PID.
- `kill -9 <PID>` : Forcefully terminate a process using SIGKILL.
- `killall <name>` : Kill all processes matching a given name.
- `nice -n 10 <cmd>` : Start a process with a specified priority.
- `renice 10 -p <PID>` : Change the priority of a running process.
