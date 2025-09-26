# pwn.college_garvit

# Hello Hackers

### Intro to Arguments

The challenge asks you to open the terminal in the pwn.college DOJO and run the hello command with a specific argument (hackers) to obtain the flag. The exercise demonstrates how commands can take arguments and how those arguments affect the command output.

### Solve

**Flag:** `pwn.college{0EFq54Mttd329QM4X6NDFjCFH28.QX3YjM1wSN0AzNzEzW}`

To solve the challenge, I first experimented with the echo command, which simply prints its arguments back onto the terminal. For example, running echo Hello outputs "Hello" while echo Hello Hackers! outputs "Hello Hackers!". Finally, I used the required hello command with the single argument hackers, which successfully returned the flag.

```bash
hacker@hello-intro-to-arguments:~$ echo Hello
Hello
hacker@hello-intro-to-arguments:~$ echo Hello Hackers!
Hello Hackers!
hacker@hello-intro-to-arguments:~$ hello hackers
Success! Here is your flag:
pwn.college{ED8dTHSj__ETgZgz0Py5_W8621V.QX4YjM1wSN0AzNzEzW}
```

New Learnings
I learned the concept of arguments in Linux commands:

The first word is the command, and everything after it is treated as an argument.

Commands like echo simply repeat their arguments back as output.

Some commands require specific arguments (like hello hackers) to execute successfully.

References
None