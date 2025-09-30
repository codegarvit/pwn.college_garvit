# pwn.college_garvit
# Praciting Piping

# Duplicating Pipe Data With Tee
This challenge introduces the tee command, a tool that acts like a "T-splitter" for command-line pipes. It reads from standard input and writes that data to both standard output and a specified file simultaneously. The task is to use tee to debug a pipeline where one program's output needs to be correctly piped into another.

### Solve
**Flag:** `pwn.college{kTX6l2sbuhYDndA5iogxy67upCx.QX1cDN1wSN0AzNzEzW}`
Information Gathering: The initial problem is that piping /challenge/pwn directly to /challenge/college fails. To understand why, tee is inserted into the pipeline to capture the output of /challenge/pwn into a file for later inspection.

Bash

/challenge/pwn | tee /tmp/intercept | /challenge/college
This command still results in an error from /challenge/college, but it successfully saves the output from /challenge/pwn into the /tmp/intercept file.

Analysis: The contents of the intercepted file are then examined.

Bash

cat /tmp/intercept
This reveals the usage instructions for the /challenge/pwn program, showing that it must be run with a secret argument to produce the correct output code. The captured text indicates the correct usage is /challenge/pwn --secret I0hpMZHK.

Final Execution: Armed with this new knowledge, a final, correct pipeline is constructed. The /challenge/pwn command is run with its required arguments, and its output (the now-correct secret code) is piped directly into /challenge/college, which processes it and prints the flag.

```bash
hacker@variables~storing-command-output:~$ PWN=$(/challenge/run)
Congratulations! You have read the flag into the PWN variable. Now print it out
and submit it!
hacker@variables~storing-command-output:~$ echo $PWN
pwn.college{kTX6l2sbuhYDndA5iogxy67upCx.QX1cDN1wSN0AzNzEzW}
```
    
### New Learnings
1. The tee Command: The core lesson is the use of tee to split a data stream. This allows you to view data on the screen while simultaneously saving it to a file or passing it to another command.

2. Debugging Pipelines: This challenge demonstrates a powerful, real-world use case for tee. By capturing the data at an intermediate step in a pipeline, you can easily debug complex command chains and understand why they might be failing.
### References 
None