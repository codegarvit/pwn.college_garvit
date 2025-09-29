# pwn.college_garvit
# Praciting Piping

# Redirecting More Output
This challenge demonstrates that output redirection can be used on any command, not just echo. The task is to run a program, /challenge/run, which will only produce the flag if its standard output (stdout) is redirected to a file named myflag. The challenge also explains that the program uses standard error (stderr) for status messages, which is why some text still appears on the terminal during redirection.

### Solve
**Flag:** `pwn.college{UzKwfupZ4-yyF4Pl2cpAvXJBi8q.QX0YTN0wSN0AzNzEzW}`
The solution is a two-step process: first, run the program with its output redirected to capture the flag, and second, read the file containing the captured flag.

1. Run and Redirect: The /challenge/run program is executed, and the > operator is used to redirect its standard output into the file named myflag.

2. Read the Flag: After the first command completes, the flag is now stored in the myflag file. The cat command is used to display the contents of this file, revealing the flag.

```bash
hacker@piping~redirecting-more-output:~$ /challenge/run > myflag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~redirecting-more-output:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{0uagAFxXezgXmxGxcqlyK3RUH9E.QX1YTN0wSN0AzNzEzW}
```
    
### New Learnings
1. Universal Redirection: The main lesson is that output redirection (>) is a universal shell feature that can capture the standard output of any program or command, not just echo.

2. Standard Output (stdout) vs. Standard Error (stderr): This challenge provides a practical example of the two primary output streams. A program can send its main result (the flag) to stdout while sending status messages and errors to stderr. This allows you to save the important output to a file while still seeing progress messages on your screen.

### References 
None