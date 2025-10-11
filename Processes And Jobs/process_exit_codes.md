# pwn.college_garvit
# Processes and Jobs

# Process Exit Codes
This challenge explains that every command exits with an exit code to show if it succeeded (usually 0) or failed (a non-zero value).We can access the exit code of the most recently-terminated command using the special ? variable" (as $?).

### Solve
**Flag:** `pwn.college{Axrkdlokqsb8o_NDNWusJKGew3z.QX5YDO1wSN0AzNzEzW}`

The solution is a two-step process: first run the program that generates the exit code, then immediately run the second program, using the $? variable to pass the code as an argument.

The Goal: You need to get the "exit code" from /challenge/get-code and use it as an "argument" for /challenge/submit-code.

The Process:

First, the /challenge/get-code program is run. It exits and sets the special $? variable to its exit code.
Second, the /challenge/submit-code program is run immediately after. The shell sees $?, replaces it with the exit code from the previous command, and passes it as the argument.
The Result: The /challenge/submit-code program receives the correct code and prints the flag.

```bash
hacker@processes~process-exit-codes:~$ /challenge/get-code
Exiting with an error code!
hacker@processes~process-exit-codes:~$ /challenge/submit-code $?
CORRECT! Here is your flag:
pwn.college{Axrkdlokqsb8o_NDNWusJKGew3z.QX5YDO1wSN0AzNzEzW}
```
    
### New Learnings
1. The $? Variable: The main lesson is the use of the "special ? variable", which you access as $? to read its value. It always contains the exit code of the most recently-terminated command.

2. Meaning of Exit Codes: Commands use exit codes to report their status. A 0 typically means the command "succeeded", while a non-zero value means it "fail[ed]".

### References 
None