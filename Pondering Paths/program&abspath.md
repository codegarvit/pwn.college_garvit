# pwn.college_garvit
# Pondering Paths

# Program and Absolute Path
This challenge introduces the concept of absolute paths in Linux. Instead of running a program by its relative path or name, we are required to execute it by specifying its absolute location in the filesystem.

### Solve
**Flag:** `pwn.college{k4V7FVlJmvU_fj_QXGMTNWNtkr-.QX1QTN0wSN0AzNzEzW}`

In this level, the challenge program is named run, and it resides in the /challenge directory, which itself is directly inside the root directory (/). 
To solve the challenge, I executed the program using its absolute path:

```bash
hacker@paths~program-and-absolute-paths:~$ /challenge/run
Correct!!!
/challenge/run is an absolute path! Here is your flag:
pwn.college{k4V7FVlJmvU_fj_QXGMTNWNtkr-.QX1QTN0wSN0AzNzEzW}
```
The flag was successfully displayed after running the program.

### New Learnings
I learned the concept of absolute paths in Linux:

1. An absolute path specifies the full location of a file or program starting from the root directory (/).
2. Unlike relative paths (which depend on your current working directory), absolute paths always work regardless of where you are in the filesystem.

### References 
None