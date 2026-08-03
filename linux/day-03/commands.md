# Viewing & Editing Files

## Viewing files

- `cat <file>` : Display the contents of a file.
- `cat -n <file>` : Display file contents with line numbers.
- `more <file>` : View a file one screen at a time.
- `less <file>` : View a file with forward/backward scrolling and search support.
- `head -n 10 <file>` : Display the first 10 lines of a file.
- `tail -n 10 <file>` : Display the last 10 lines of a file.
- `tail -f <file>` : Monitor a file in real time (press **Ctrl + C** to stop).
- `wc <file>` : Count lines, words, and characters in a file.
- `wc -l <file>` : Count only the number of lines in a file.
- `sed -n "5,10p" <file>` : Print lines 5 through 10 of a file.
- `diff -u file1 file2` : Compare two files using the unified diff format.

## Redirection and pipes

- `cmd > <file>` : redirects output to a file ,overwritimg existing content.
- `cmd >> <file>` : appends output to a file , appending to existin content.
- `cmd < <file>` : Uses the file content as input to command.
- `cmd1 | cmd2` :Pipe- sends the input of one command to another.
- `cmd 2> errfile`:redirect only error messaage(stderr) to a file.
- `cmd1 ; cmd2` : Run both commands.
- `cmd &` : Runs commans in background.
- `ls "*.txt"` : Match any character.
- `ls file?.txt` : Match exactly one character.
- `cmd1 && cmd2` : First excecute the first command and if success then run second command.
- `cmd ||cmd2` : Runs the right side only if the left fails.

## Numerical Comparison Operators

- `-eq` : Equal to (`==`).
- `-ne` : Not equal to (`!=`).
- `-gt` : Greater than (`>`).
- `-lt` : Less than (`<`).
- `-ge` : Greater than or equal to (`>=`).
- `-le` : Less than or equal to (`<=`).
