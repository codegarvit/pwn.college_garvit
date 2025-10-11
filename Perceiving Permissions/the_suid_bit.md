# pwn.college_garvit
# Perceiving Permissions

# The SUID Bit  
This challenge covers the Set User ID (SUID) permissions bit. When this bit is set on a program, the program will execute as the owner user (in this case, root), regardless of who runs it. The task is to add the SUID bit to the /challenge/getroot program in order to spawn a root shell and then cat the flag.

### Solve
**Flag:** `pwn.college{Mp93vLuas0RWdrbWzwI-7GcZvgN.QXxEjN0wSN0AzNzEzW}`
The solution requires us to first make the program SUID, then run it to get a root shell, and finally read the flag.

1. The Goal: The challenge is to get a "root shell" to read the flag. We can do this by using chmod to modify the /challenge/getroot program.

2. The Process:
 - First, we "add the SUID bit" to the program using the u+s mode with chmod.
 - Second, we run the program. Because the SUID bit is set, it is now "running as root" and gives us a new shell with a # prompt.
  - Third, from the new root shell, we can read the flag.

3. The Result: The cat command prints the flag.

```bash
hacker@permissions~changing-file-ownership:~$ chown hacker /flag
hacker@permissions~changing-file-ownership:~$ cat /flag
pwn.college{Mp93vLuas0RWdrbWzwI-7GcZvgN.QXxEjN0wSN0AzNzEzW}
```
    
### New Learnings
1. The SUID Bit: We learned that the SUID bit is a special permission that makes an executable program run with the permissions of the file's owner, not the user running it.

2. Setting SUID: We learned that we can set a file's SUID bit by using chmod with the u+s mode

### References 
None