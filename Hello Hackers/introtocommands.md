# pwn.college_garvit
# Hello Hackers

# Intro to Commands
This challenge serves as the first introduction to invoking commands in the pwn.college dojo. The goal is to run a specific command, `hello`, to obtain the flag.

### Solve
**Flag:** `pwn.college{0Efq54Mttd329QM4X6nDfJCFH28.QX3YjM1wSN0AzNzEzW}`

In this challenge, the task was to run the very first Linux command inside the pwn.college DOJO terminal. The instructions explained that typing a command and pressing Enter would execute it and display its output.

The example given was whoami, which simply prints the current username (hacker).
For this challenge, we needed to run the hello command to retrieve the flag.

```
hacker@hello~intro-to-commands:~$ whoami
hacker
hacker@hello~intro-to-commands:~$ hello
Success! Here is your flag:
pwn.college{0Efq54Mttd329QM4X6nDfJCFH28.QX3YjM1wSN0AzNzEzW}
```
    
### New Learnings
I learned how to invoke basic Linux commands in the terminal. I also understood the importance of case sensitivity in Linux commands. Even small differences like uppercase vs lowercase make a big difference in execution. This was a great first step in learning command-line basics.

### References 
None