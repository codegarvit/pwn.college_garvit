# pwn.college_garvit
# Perceiving Permissions

# Changing File Ownership
This challenge introduces process substitution, a shell feature that allows the output of a command to be treated as a temporary file. The task is to use this feature with the diff command to compare the live outputs of two programs—/challenge/print_decoys and /challenge/print_decoys_and_flag—to find the single line of text that is different, which will be the flag.

### Solve
**Flag:** `pwn.college{Mnz4Dqgn1BqGuOIt-_lZuUiyxnU.0lNwMDOxwSN0AzNzEzW}`
The goal is to provide the diff command with two inputs, but instead of creating temporary files on disk, we use process substitution to create them on-the-fly from the output of the two programs.

1. The Tool (diff): The diff command is used to compare inputs line by line. It typically operates on two filenames, for example, diff file1 file2.

2. The Technique (Process Substitution): The challenge requires using the <(command) syntax. When the shell sees this, it runs the command and connects its standard output to a special file (a named pipe). It then replaces the entire <(command) expression with the path to that special file.

3. Command Construction: The final command is built by providing diff with two arguments, each created by process substitution:
The first argument is <(/challenge/print_decoys), which provides the output of the first program as a "file."
The second argument is <(/challenge/print_decoys_and_flag), which provides the output of the second program as another "file."

```bash
hacker@permissions~changing-file-ownership:~$ chown hacker /flag
hacker@permissions~changing-file-ownership:~$ cat /flag
pwn.college{Mp93vLuas0RWdrbWzwI-7GcZvgN.QXxEjN0wSN0AzNzEzW}
```
    
### New Learnings
1. Process Substitution <(command): The primary lesson is how to use this powerful shell feature to make a command's output appear as a file to another command. This is invaluable for tools that are designed to read from files.

2. The "Everything is a File" Philosophy: This is a practical example of the Unix/Linux design philosophy, where resources like the output of a running program can be accessed via the filesystem, just like a regular file.

### References 
None