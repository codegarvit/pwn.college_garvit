# pwn.college_garvit
# Perceiving Permissions

# Executable Files
This challenge is about execute permissions. It explains that Linux will only let us invoke a program if we have execute-access to the program file. The task is to get the flag from the /challenge/run program, but we must first make it executable.

### Solve
**Flag:** `pwn.college{4omQ9v49gu1VrjoDvPFyYYdDl9U.QXyEjN0wSN0AzNzEzW}`
The solution requires us to first use the chmod command to add the execute permission to the file, and then run the file.

1. The Goal: The challenge is to run the /challenge/run program, but its permissions are set so that our user cannot execute it. The execution will fail until we change the permissions.

2. The Process:
 - First, we make the file executable. We use the chmod command to add (+) the execute (x) permission for our user (u).
 - Second, now that we have execute-access to the program file, we can invoke it.

3. The Result: The /challenge/run command prints the flag.

```bash
hacker@permissions~executable-files:~$ chmod u+x /challenge/run
hacker@permissions~executable-files:~$ /challenge/run
Successful execution! Here is your flag:
pwn.college{4omQ9v49gu1VrjoDvPFyYYdDl9U.QXyEjN0wSN0AzNzEzW}
```
    
### New Learnings
1. Execute Permission: The main lesson is that a file needs the execute bit (x) set in its permissions before the shell will run it as a program.

2. Making Files Executable: We learned that chmod u+x is a way to add execute permission for the user, which will make a file executable.

### References 
None