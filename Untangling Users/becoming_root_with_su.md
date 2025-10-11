# pwn.college_garvit
# Untangling Users

# Becoming Root With su
This challenge covers the su (substitute user) command, which is an action Linux users take to become root. The task is to provide the correct root password to the su command to gain root access and then read the flag.

### Solve
**Flag:** `pwn.college{cTW2-IscHVTLX0sJ84OduUnio88.QX1UDN1wSN0AzNzEzW}`

1. The Goal: The challenge is to elevate privileges to become the root user, who has access to read the flag.

2. The Tool: The challenge introduces the su command. It is a setuid binary that runs as root, but it first checks to make sure the user knows the root password before starting a root shell.

3. The Process:
 - First, the su command is run.
 - The command will then ask for a Password:. The password given in the challenge, hack-the-planet, is typed, and Enter is pressed. The password will not be visible on the screen.
 - After successful authentication, the command prompt changes from $ to #, which shows you are now in a root shell.
 - Getting the Flag: With root access, the flag can be read from /flag.

 ```bash
hacker@users~becoming-root-with-su:~$ su
Password:
root@users~becoming-root-with-su:/home/hacker# cat /flag
pwn.college{cTW2-IscHVTLX0sJ84OduUnio88.QX1UDN1wSN0AzNzEzW}
root@users~becoming-root-with-su:/home/hacker#
```
    
### New Learnings
1. The su Command: The main lesson is using the su command to become root. It requires you to provide the root password.

2. Root Privileges: This challenge shows that root is a special user with access to everything. A command prompt ending in # is a common sign that you are running a root shell.

3. Setuid Binaries: The challenge mentions that su is a setuid binary. This is a special file permission that allows a user to run that program with the privileges of the file's owner (in this case, root).

### References 
None