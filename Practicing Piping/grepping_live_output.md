# pwn.college_garvit
# Praciting Piping

# Grepping Live Output
This challenge introduces the pipe operator (|), a core feature of the shell that allows you to connect the output of one command directly to the input of another. This avoids the need for a temporary file, creating a more efficient and elegant workflow.

### Solve
**Flag:** `pwn.college{4F8I6-jlpNMdogPRXf8g4CxfbJH.QX5EDO0wSN0AzNzEzW}`
The solution involves constructing a single command that "pipes" the live output from the /challenge/run program directly into the grep command for real-time filtering. This replaces the two-step "save then search" method from the previous level.

1. The "Producer" Command: The command that generates the data, /challenge/run, is placed on the left side of the pipe. When executed, it begins writing its hundreds of thousands of lines of text to its standard output.

2. The "Consumer" Command: The command that processes the data, grep, is placed on the right side of the pipe. It's given the search pattern pwn.college to look for the flag.

3. Connecting with the Pipe: The pipe operator (|) is placed between the two commands. It takes the standard output from /challenge/run and connects (or "pipes") it directly to the standard input of grep.

```bash
hacker@piping~grepping-live-output:~$ /challenge/run | grep pwn.college
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stdout : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/8b4vn1iyn6kqiisjvlmv67d1c0p3j6wj-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stdout!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{4F8I6-jlpNMdogPRXf8g4CxfbJH.QX5EDO0wSN0AzNzEzW}
```
    
### New Learnings
1. The Pipe Operator (|): The primary lesson is the use of the pipe operator to chain commands together, feeding the standard output of one command into the standard input of the next. This is one of the most powerful concepts in the shell.

2. Live Filtering: Piping allows for the real-time filtering of a command's output. This is extremely useful for searching through logs, monitoring processes, or any task where you need to find specific information within a large or continuous stream of data.

3. Efficiency: Using pipes is more efficient than using temporary files because the data is passed between processes in memory, avoiding the slower process of writing to and reading from a disk. It also simplifies commands and avoids the need to clean up temporary files.

### References 
None