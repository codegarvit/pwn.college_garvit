# pwn.college_garvit
# Praciting Piping

# Grepping Errors
This challenge explains that the pipe (|) operator only redirects standard output (stdout), not standard error (stderr). The task is to learn how to grep a program's error stream by using the special shell operator 2>&1 to first merge the error stream into the standard output stream, which can then be piped.

### Solve
**Flag:** `pwn.college{g1GLNbt_v1wJilkpfvEDiHG1Vch.QX1ATO0wSN0AzNzEzW}`
The solution requires constructing a command that first merges the two output streams and then pipes the result to grep.

1. The Problem: The /challenge/run program for this level produces its output, including the flag, on standard error (stderr, file descriptor 2). A standard pipe (/challenge/run | grep ...) would fail because the pipe only listens to standard output (stdout, file descriptor 1).

2. The Solution (Stream Merging): The shell provides the 2>&1 operator to solve this. This syntax redirects file descriptor 2 (stderr) to the same destination as file descriptor 1 (stdout), effectively merging the error messages into the standard output stream.

3. Command Construction: The final command is a three-part chain:
 - First, the /challenge/run program is executed.
 - Second, its standard error is merged into its standard output with 2>&1.
 - Finally, the pipe | takes this newly combined stream and sends it to grep pwn.college for filtering.

The complete command is:

```bash
hacker@piping~grepping-errors:~$ /challenge/run 2>&1 | grep pwn.college
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stderr : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stderr to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/8b4vn1iyn6kqiisjvlmv67d1c0p3j6wj-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stderr!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{g1GLNbt_v1wJilkpfvEDiHG1Vch.QX1ATO0wSN0AzNzEzW}
```
    
### New Learnings
1. The 2>&1 Operator: The main lesson is the use of 2>&1 to redirect standard error to standard output. This is a crucial technique for capturing a command's complete output.

2. Pipe Limitations: The challenge explicitly teaches that the | operator only works on standard output. Understanding this is key to debugging scripts and command chains.

3. Processing Error Streams: By merging stderr into stdout, you can use powerful text-processing tools like grep, sed, and awk to filter, search, and manipulate error messages, which is invaluable for debugging and log analysis.

### References 
None