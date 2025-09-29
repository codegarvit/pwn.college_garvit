# pwn.college_garvit
# File GLobbing

# Redirecting Output
This challenge introduces the concept of redirecting a command's standard output (stdout) to a file using the > character. The task is to apply this knowledge to write the word "PWN" into a new file named "COLLEGE".

### Solve
**Flag:** `pwn.college{UzKwfupZ4-yyF4Pl2cpAvXJBi8q.QX0YTN0wSN0AzNzEzW}`
The solution requires a single command that combines the echo command with the output redirection operator.

1. Generate the String: The echo PWN command is used to produce the required string "PWN".

2. Redirect the Output: The > operator is appended to the command to redirect the output.

3. Specify the Destination: The filename COLLEGE is provided as the destination for the redirected output.

```bash
hacker@piping~redirecting-output:~$ echo PWN > COLLEGE
Correct! You successfully redirected 'PWN' to the file 'COLLEGE'! Here is your
flag:
pwn.college{UzKwfupZ4-yyF4Pl2cpAvXJBi8q.QX0YTN0wSN0AzNzEzW}
```
    
### New Learnings
1. Standard Output (stdout): By default, many commands print their results to a stream called standard output, which is usually your terminal screen.

2. The > Redirection Operator: The primary lesson is that the > operator intercepts a command's standard output and writes it to a specified file instead. If the file doesn't exist, it's created. If it does exist, its contents are overwritten.
### References 
None