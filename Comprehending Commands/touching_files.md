# pwn.college_garvit
# Comprehending Commands

# Touching Files
This challenge introduces the touch command, a simple utility for creating new, empty files. The task is to create two specific files, /tmp/pwn and /tmp/college, and then execute a verification script to get the flag.

### Solve
**Flag:** `pwn.college{0Q4Eqp5_caAA6Q0KI9QFNbMMYmd.QX2kDM1wSN0AzNzEzW}`
The solution requires using the touch command to create the specified files before running the checker.

1. The Goal: The challenge requires the creation of two empty files at the absolute paths /tmp/pwn and /tmp/college.

2. The Tool: The touch command is the specified tool for creating blank files. A key feature of touch is its ability to accept multiple arguments, allowing for the creation of several files with a single command.

3. The Commands:
 - First, the touch command is used with both file paths as arguments. This efficiently creates both required files in the /tmp directory.
 - Second, the verification script is run. This script checks for the existence of both files and provides the flag upon successful verification.

```bash
hacker@commands~touching-files:~$ touch /tmp/pwn /tmp/college
hacker@commands~touching-files:~$ /challenge/run
Success! Here is your flag:
pwn.college{UdOvxhRUWFQHtIbvoBPYTjlAtS7.QXwMDO0wSN0AzNzEzW}
```
    
### New Learnings
1. The touch Command: The main lesson is the use of the touch <filename(s)> command to quickly create new, empty (zero-byte) files.

2. Creating Multiple Files: The touch command can create multiple files at once by simply listing them as space-separated arguments.

3. The /tmp Directory: This challenge uses the /tmp directory, a standard location in Linux/Unix filesystems for storing temporary files that don't need to persist after a system reboot.
### References 
None