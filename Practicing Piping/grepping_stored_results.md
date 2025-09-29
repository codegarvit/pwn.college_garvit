# pwn.college_garvit
# Praciting Piping

# Grepping Stored Results
This challenge combines two previously learned skills, output redirection (>) and searching with grep, to demonstrate a common command-line workflow. The goal is to capture the large output of a program in a file and then search that file for the flag.

### Solve
**Flag:** `pwn.college{kSWxWOcsYMypgwI6aluqdMnAW-A.QX4EDO0wSN0AzNzEzW}`
The solution follows the two-stage "capture then process" workflow. The core idea is that running a program with a huge amount of output directly to the terminal is inefficient. It's better to save that output to a file first and then use a specialized tool like grep to find the needed information.

1. Capture the Program's Output: The first step is to execute the /challenge/run program. Its standard output (stdout), which contains the flag amidst thousands of other lines, is redirected using the > operator into a file located at /tmp/data.txt.

2. Search the Stored Results: With all the output now saved, the grep command is used to search the /tmp/data.txt file. The search pattern pwn.college is used, as this is the standard prefix for flags in these challenges. grep efficiently reads the entire file and prints only the line that matches the pattern, revealing the flag.

```bash
hacker@piping~grepping-stored-results:~$ /challenge/run > /tmp/data.txt
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /tmp/data.txt
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to a file called /tmp/data.txt. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~grepping-stored-results:~$ grep pwn.college /tmp/data.txt
pwn.college{kSWxWOcsYMypgwI6aluqdMnAW-A.QX4EDO0wSN0AzNzEzW}
```
    
### New Learnings
1. The Capture-then-Process Workflow: A fundamental technique on the command line is to save the output of a command to a file first, and then run subsequent commands (like grep, sed, awk) to process that saved data.

2. Combining Command-Line Tools: This challenge is a practical example of the Unix philosophy: using simple, specialized tools (> and grep) together to accomplish a more complex task.

3. stdout vs. stderr: The challenge clearly demonstrates how a program can use standard output (stdout) for its primary data and standard error (stderr) for status messages, allowing for clean data capture while still providing user feedback.

### References 
None