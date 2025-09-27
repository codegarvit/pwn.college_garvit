# pwn.college_garvit
# Digesting Documentation

# Moving Files
This challenge introduces the mv command, which is used to move or rename files and directories. The task is to move a specific file, located at /flag, to a new destination, /tmp/hack-the-planet. After the file has been moved, a checker script must be run to verify the solution and receive the flag.

### Solve
**Flag:** `pwn.college{0qPpxLMR1rbxkx0bTdoMtiz30sU.0VOxEzNxwSN0AzNzEzW}`

The solution requires two commands: one to perform the move operation and another to run the verification script.

1. Move the File: The mv command is used with the source and destination paths. The source is the original file (/flag), and the destination is the new location and name (/tmp/hack-the-planet).

2. Get the Flag: The checker script is run. It confirms that the file is no longer at /flag and now exists at /tmp/hack-the-planet, then prints the flag.

```bash
hacker@commands~moving-files:~$ mv /flag /tmp/hack-the-planet
Correct! Performing 'mv /flag /tmp/hack-the-planet'.
hacker@commands~moving-files:~$ /challenge/check
Congrats! You successfully moved the flag to /tmp/hack-the-planet! Here it is:
pwn.college{0qPpxLMR1rbxkx0bTdoMtiz30sU.0VOxEzNxwSN0AzNzEzW}
```
    
### New Learnings

1. The mv Command: The core lesson is the syntax and function of mv <source> <destination>. This command is a fundamental utility for organizing files.

2. Moving and Renaming: The mv command can perform two related actions. If the destination is an existing directory, the source file is moved into it. If the destination is a new path with a new filename (as in this challenge), the file is moved and renamed in a single step.

3. Filesystem Operations: This challenge provides a practical example of a common filesystem operation—relocating a file from one part of the directory tree to another.

### References 
None