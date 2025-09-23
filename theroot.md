# pwn.college_garvit
# Pondering Paths

# The Root
This challenge introduces the concept of the filesystem hierarchy in Linux and the idea of using absolute paths to run programs. In Linux, the filesystem starts at / (root), which contains all other directories, configuration files, programs, and important resources.

### Solve
**Flag:** `pwn.college{0Efq54Mttd329QM4X6nDfJCFH28.QX3YjM1wSN0AzNzEzW}`
In this exercise, a program called pwn is placed directly inside the / directory. The task is to invoke it using its absolute path and capture the flag.
To solve the challenge, I launched the terminal and executed the program by providing its full path starting from the root directory.Since the program was located at /pwn, I ran:
```
hacker@paths~the-root:~$ /pwn
BOOM!!!
Here is your flag:
pwn.college{cR-uJzXqgXI-BxbmD516UtzMwyL.QX4cTO0wSN0AzNzEzW}
```
    
### New Learnings
I learned about:

1. Root directory (/) – the top of the Linux filesystem hierarchy.
2. Absolute paths – a path that starts with / and specifies the full location of a file or program.
3. Programs can be executed by providing their absolute path, even if they are not in the current working directory or in the $PATH.

### References 
None