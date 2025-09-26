# pwn.college_garvit
# Hello Hackers

# Implicit Relative Paths
This challenge introduces the concept of explicitly referencing the current directory when executing a program. By default, Linux does not search the current directory for executables when you type a “naked” command (like run). This is a deliberate safety measure to prevent accidentally running programs in your current folder that share names with important system utilities.
Instead, to tell Linux to execute a program in the current directory, you must prefix it with ./.

### Solve
**Flag:** `pwn.college{MKN1Q0SKZA1XqYCI06dk4yBMc-l.QXxUTN0wSN0AzNzEzW}`
The task: run the challenge binary from /challenge, explicitly telling Linux to look in the current directory.

1. Navigate into the /challenge directory:
```bash
hacker@paths~implicit-relative-path:~$ cd /challenge
```
2. explicitly execute the program using ./run:
```bash
hacker@paths~implicit-relative-path:/challenge$ ./run
Correct!!!
./run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{MKN1Q0SKZA1XqYCI06dk4yBMc-l.QXxUTN0wSN0AzNzEzW}
```
    
### New Learnings
The key takeaways are:

1. Linux does not look in the current directory (.) when searching for executables by default.
2. To execute a program in the current directory, you must prefix it with ./.
3. This design prevents accidental execution of malicious or unintended binaries with names identical to system commands.
4. Relative paths beginning with ./ explicitly instruct Linux to look in the present working directory.

### References 
None