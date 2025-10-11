# pwn.college_garvit
# Perceiving Permissions

# Groups And Files  
This challenge explains that files in Linux have both an owning user and an owning group. It introduces the chgrp (change group) command for changing the group ownership of a file. 

### Solve
**Flag:** `pwn.college{Mp93vLuas0RWdrbWzwI-7GcZvgN.QXxEjN0wSN0AzNzEzW}`
The solution is a two-step process where we first change the group ownership of the /flag file to a group we are a member of, and then we read the file.

1. The Goal: The /flag file is owned by the root group, but the hacker user is not a member of that group, so we cannot read it. The challenge makes the file "readable by whatever group owns it," so we need to change its group to one we belong to.

2. The Tool: The challenge introduces the chgrp command. For this challenge, we can invoke chgrp as the hacker user, an action that typically requires root access.

3. The Commands:
 - First, we use the id command to see that our user is a member of the hacker group. We then use chgrp to change the /flag file's group to hacker.
 - 
 
 ```bash
hacker@permissions~groups-and-files:~$ id
uid=1000(hacker) gid=1000(hacker) groups=1000(hacker)
hacker@permissions~changing-file-ownership:~$ chown hacker /flag
hacker@permissions~changing-file-ownership:~$ cat /flag
pwn.college{Mp93vLuas0RWdrbWzwI-7GcZvgN.QXxEjN0wSN0AzNzEzW}
```
    
### New Learnings
1. Group Ownership: We learned that Files have both an owning user and group. Group ownership is a common way to control access to system resources for multiple users.

2. The chgrp Command: We learned how to use the chgrp [group] [file] command to change the group that owns a file.

3. The id Command: We learned that the id command can be used to check what groups you are part of.

### References 
None