# pwn.college_garvit
# Comprehending Commands

# Removing Files
This challenge introduces the mkdir command, used for creating new directories (folders) in the filesystem. The task is to first create a directory named pwn inside the /tmp directory, and then create a file named college inside that new directory. Finally, a verification script must be run to get the flag.

### Solve
**Flag:** `pwn.college{0Q4Eqp5_caAA6Q0KI9QFNbMMYmd.QX2kDM1wSN0AzNzEzW}`

The solution requires a sequence of three commands: one to create the directory, one to create the file in the correct location, and one to run the checker.

1. Create the Directory: The mkdir command is used with the absolute path /tmp/pwn to create the required directory.

2. Create the File: The touch command is used to create the college file. Crucially, the path must specify that the file goes inside the newly created /tmp/pwn directory.

3. Get the Flag: The provided checker script is run, which verifies that both the directory and the file exist in the correct locations before awarding the flag.

```bash
hacker@commands~removing-files:~$ rm delete_me
hacker@commands~removing-files:~$ /challenge/check
Excellent removal. Here is your reward:
pwn.college{0Q4Eqp5_caAA6Q0KI9QFNbMMYmd.QX2kDM1wSN0AzNzEzW}
```
    
### New Learnings

1. The mkdir Command: The primary lesson is the use of mkdir <path> to create new directories in the filesystem.

2. Hierarchical Structure: This exercise demonstrates the nested nature of filesystems, where you can create directories and then place files or other directories inside them.

3. Path Specificity: Solving the challenge correctly requires using precise absolute paths to ensure both the directory and the file are created in the exact locations the verification script expects.

### References 
None