# pwn.college_garvit
# Perceiving Permissions

# Groups And Files  
This challenge covers file ownership and the chown (change owner) command. The /flag file is owned by the root user, which prevents us from reading it as the hacker user. The task is to practice changing the owner of the /flag file to the hacker user, and then read the flag.

### Solve
**Flag:** `pwn.college{Mnz4Dqgn1BqGuOIt-_lZuUiyxnU.0lNwMDOxwSN0AzNzEzW}`
The solution is a two-step process where we first take ownership of the file and then read it.

1. The Goal: The /flag file is owned by root, which is why an attempt to cat /flag results in "Permission denied". To read the file, we must first change its owner to our user, hacker.

2. The Tool: The challenge introduces the chown command, which is used to "change the ownership of files". For this challenge, we are given the ability to run chown, an action that typically requires you to be root.

3. The Commands:
 - First, we use chown to change the owner of /flag to hacker.
 - Second, now that the hacker user owns the file, we have permission to read it with cat.

 4. The Result: The cat command prints the flag.

```bash
hacker@permissions~changing-file-ownership:~$ chown hacker /flag
hacker@permissions~changing-file-ownership:~$ cat /flag
pwn.college{Mp93vLuas0RWdrbWzwI-7GcZvgN.QXxEjN0wSN0AzNzEzW}
```
    
### New Learnings
1. File Ownership: The main lesson is that "Every file in Linux is owned by a user on the system". This ownership is a key part of how file permissions work.

2. The chown Command: We learned to use the chown [username] [file] command to change the ownership of files.

### References 
None