# Background & Foreground Jobs

- `command &` : Run a command in the background and free the terminal.
- `jobs` : List background and suspended jobs in the current shell.
- `fg %1` : Bring job 1 to the foreground.
- `bg %1` : Resume suspended job 1 in the background.
- `Ctrl + Z` : Suspend (pause) the currently running foreground job.
- `nohup command &` : Run a command so it continues after terminal logout.

---

## Additional Job Commands

- `jobs -l` : List background jobs along with their process IDs (PIDs).
- `disown %1` : Remove job 1 from the shell's job table.
- `disown -h %1` : Prevent job 1 from receiving a hangup signal when the shell exits.
- `wait %1` : Wait for job 1 to finish.
- `fg` : Bring the most recently stopped/background job to the foreground.
- `bg` : Resume the most recently suspended job in the background.
