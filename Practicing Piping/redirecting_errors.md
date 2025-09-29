# pwn.college_garvit
# Praciting Piping

# Redirecting Errors
This challenge introduces the concept of redirecting standard error (stderr) by using its file descriptor number, 2. It explains that commands have separate channels for their normal output (standard output, or stdout, FD 1) and their error or status messages (standard error, or stderr, FD 2). The task is to run the /challenge/run program and, in a single command, redirect its stdout to a file named myflag and its stderr to a file named instructions.
### Solve
**Flag:** `pwn.college{UaYOemWhDScSwOXEavlhC1Tm2OK.QX3YTN0wSN0AzNzEzW}`
The solution requires a single command that performs two redirections simultaneously.

1. Construct the Command: The /challenge/run program is executed. The standard output is redirected to myflag using the > operator, and the standard error is redirected to instructions using the 2> operator.

2. Retrieve the Flag: After the command runs, the program's normal output (the flag) is saved in the myflag file. The cat command is used to display its contents.

```bash
hacker@piping~redirecting-errors:~$ /challenge/run > myflag 2> instructions
hacker@piping~redirecting-errors:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{UaYOemWhDScSwOXEavlhC1Tm2OK.QX3YTN0wSN0AzNzEzW}
```
    
### New Learnings
1. File Descriptors: The core lesson is the concept of file descriptors (FDs) as channels for process communication, specifically FD 1 (stdout) and FD 2 (stderr).

2. Redirecting Standard Error (2>): The challenge teaches the specific syntax 2> filename for redirecting the standard error stream of a command. This is distinct from > which is a shorthand for 1> (redirecting stdout).

3. Multiple Redirections: A key takeaway is that you can redirect multiple output streams from a single command at the same time. 
### References 
None