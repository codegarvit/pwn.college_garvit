# pwn.college_garvit
# File GLobbing

# Tab Completion On Commands
This challenge demonstrates that Tab completion is a versatile shell feature that works on command names in addition to file paths. The task is to find and execute a command that starts with the prefix pwncollege. The solution requires typing this prefix and then using the Tab key to auto-complete the full command name, which, when run, will print the flag.

### Solve
**Flag:** `pwn.college{AE2UqjMNE0V8xAl7bGn3QchoHcN.0VN0EzNxwSN0AzNzEzW}`
The solution is a direct application of the Tab completion feature on a command name.

1. Type the Command Prefix: At the command prompt, the known prefix of the command is typed.

2. Use Tab Completion: The Tab key is pressed. The shell searches all directories in the $PATH environment variable for an executable command that starts with "pwncollege" and automatically completes the name.

3.  Execute the Command: With the full command name now on the line, pressing Enter executes it, printing the flag to the terminal.

```bash
hacker@globbing~tab-completion-on-commands:~$ pwncollege-25109
Correct! Here is your flag:
pwn.college{AE2UqjMNE0V8xAl7bGn3QchoHcN.0VN0EzNxwSN0AzNzEzW}
```
    
### New Learnings
1. Command Discovery: Using Tab completion on a partial command name is a useful way to discover or remember the full names of tools without having to list the contents of system directories.

2. Command Completion: The core lesson is that Tab completion works for command names, not just file and directory paths. This is a crucial feature for improving speed and accuracy in the shell.

### References 
None