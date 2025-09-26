# pwn.college_garvit
# Hello Hackers

# Position Elsewhere
This challenge teaches the concept of the current working directory in Linux and how to change it using the cd command.
Every process (like the bash shell) operates in a directory it is currently “hanging out” in. The prompt often displays this directory to the user (e.g., ~ represents the home directory).
To move between directories, we use the cd command with the path to the target directory.

### Solve
**Flag:** `pwn.college{4srKSfxGsy3pZszaVYteVXvpW4T.QX2QTN0wSN0AzNzEzW}`

In this challenge, we need to navigate (cd) to the directory specified by the challenge and then run the /challenge/run program from there.
1. First, move to the directory specified by the challenge:
```bash
hacker@paths~position-thy-self:/challenge$ cd /usr/include
```
2. Once inside the correct directory, run the challenge program:
```bash
hacker@paths~position-thy-self:/usr/include$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{4srKSfxGsy3pZszaVYteVXvpW4T.QX2QTN0wSN0AzNzEzW}
```

### New Learnings
From this challenge, I learned:

1. The current working directory is where commands are executed by default.
2. The cd (change directory) command lets us move to another directory.
3. Some challenges/programs may require us to be in a specific directory before running them.
4. The ~ symbol in the shell prompt represents the home directory of the user.

### References 
None