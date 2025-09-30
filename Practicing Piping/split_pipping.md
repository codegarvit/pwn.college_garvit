# pwn.college_garvit
# Praciting Piping

# Split Pipping stderrand stdout
This challenge is an advanced exercise in shell redirection that requires sending a program's standard output (stdout) to one program and its standard error (stderr) to a different program simultaneously, without mixing the two streams.

### Solve
**Flag:** `pwn.college{Qd9qbI38Bp_O9UNz2nVF6G8Le5C.QXxQDM2wSN0AzNzEzW}`
The goal is to run /challenge/hack and pipe its stdout to /challenge/planet and its stderr to /challenge/the. This is accomplished by creating a single command that handles each output stream separately.

1. The Problem: A standard pipe (|) only redirects stdout (file descriptor 1). A simple merge (2>&1) combines the streams, but the challenge requires keeping them separate.

2. The Tools: The solution requires combining three shell features: stderr redirection (2>), output process substitution (>(command)), and a standard pipe (|).

3. Command Construction: The final command is built by handling each stream independently:
 - Handling stderr: Since a standard pipe can't be used, we redirect stderr (2>) to a "file." This "file" is actually the input of the /challenge/the program, created on-the-fly with process substitution >(/challenge/the).
 - Handling stdout: With the stderr stream separately routed, the normal stdout stream from /challenge/hack can be piped as usual to the /challenge/planet program using the | operator.
 

```bash
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack 2> >(/challenge/the) | /challenge/planet
Congratulations, you have learned a redirection technique that even experts
struggle with! Here is your flag:
pwn.college{Qd9qbI38Bp_O9UNz2nVF6G8Le5C.QXxQDM2wSN0AzNzEzW}
```
    
### New Learnings
1. Independent Stream Control: The primary lesson is how to manage stdout and stderr as separate, independent streams and route them to different destinations. This is a powerful skill for complex scripting and program management.

2. Combining Advanced Redirection: This challenge demonstrates how to combine different shell features—file descriptor redirection (2>), process substitution (>(...)), and standard pipes (|)—all in one command to achieve a complex goal.

### References 
None