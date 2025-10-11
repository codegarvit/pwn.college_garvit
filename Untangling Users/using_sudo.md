# pwn.college_garvit
# Untangling Users

# Using Sudo
This challenge covers the sudo command, which is used for "running a command as root". Unlike su, which requires a password, sudo checks policies to determine if a user is authorized to run commands with root privileges.

### Solve
**Flag:** `pwn.college{khluq5gb70q01s0VlgqCJLyfwcP.QX3ATO0wSN0AzNzEzW}`
The solution requires prepending the sudo command to the command we need to run with elevated privileges.

1. The Goal: The challenge is to read the flag. We can assume the flag is in a protected file like /flag, which a normal user would get "Permission denied" trying to read.

2. The Tool: The challenge gives us sudo access. We use the sudo command to run another command (like cat /flag) as the root user.

3. The Final Command: We combine sudo with the cat /flag command.

4. The Result: This command runs cat /flag with root privileges. Because root has access to all files, it can read the flag file, and the command prints the flag.

```bash
hacker@users~using-sudo:~$ sudo cat /flag
pwn.college{oVWY2LvixKWZhwKf4429GDxTCd7.QX4UDN1wSN0AzNzEzW}
```
    
### New Learnings
1. The sudo Command: The main lesson is how sudo is used for "running a command as root". It is a common utility that Linux users take for system administration.

2. sudo vs. su: We learned that sudo is different from su. While su starts a new root shell after password authentication, sudo runs a single command as root after checking policies in /etc/sudoers.

### References 
None