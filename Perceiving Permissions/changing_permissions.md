# pwn.college_garvit
# Perceiving Permissions

# Changing Permissions
This challenge covers file permissions and the chmod (change mode) command. We see that the /flag file is owned by the root user and its permissions are set so that all other users have no access to the file. The task is to change the permissions of the /flag file to read it.

### Solve
**Flag:** `pwn.college{4lpBd2sLoXyozsieoTMAOuoVspN.QXzcjM1wSN0AzNzEzW}`
The solution is a two-step process where we first use chmod to add the necessary read permission and then use cat to read the file.

1. The Goal: The permissions on /flag (-r-------) only give the owning user (root) the ability to read the file. To read it as the hacker user, we must make it readable.

2. The Tool: The challenge introduces the chmod command for modifying an existing mode. It uses a format where we specify who to change permissions for (u for user, g for group, o for other), how to change them (+ to add, - to remove), and what permission to change (r for read, w for write, x for execute).

3. The Commands:
 - Since our hacker user is not the owner or in the file's group, we are considered an "other" user. We need to add read permission for "other". The mode string for this is o+r.
  - After we "change the permissions," we can use cat to read the file.

4. The Result: The cat command prints the flag.

```bash
hacker@permissions~changing-permissions:~$ chmod o+r /flag
hacker@permissions~changing-permissions:~$ cat /flag
pwn.college{4lpBd2sLoXyozsieoTMAOuoVspN.QXzcjM1wSN0AzNzEzW}
```
    
### New Learnings
1. The chmod Command: The main lesson is using the chmod command to change file permissions.The WHO+/-WHAT mode allows us to tweak permissions for the "user," "group," and "other".

2. Permission Structure: We learned that access permissions in Linux are split into three sets: for the "owning user," the "owning group," and "all other users".

3. rwx Permissions: We learned what each character represents: r for read, w for write, and x for execute.

### References 
None