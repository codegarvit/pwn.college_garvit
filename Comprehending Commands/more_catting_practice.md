# pwn.college_garvit
# Comprehending Commands

# More Catting Practice
This challenge is similar to the previous one, but the flag is placed in a "crazy directory" with a complex path. The ability to change directories using cd is disabled, forcing the use of cat with an absolute path. The path to the flag is revealed when the challenge starts.

### Solve
**Flag:** `pwn.college{IJJuluY9bMj8uLLuGYEKknA_0G4.QXwITO0wSN0AzNzEzW}`

The main constraint here is that the cd command is disabled. This means you cannot navigate into the directory where the flag is located.

When the challenge starts, it prints the full, absolute path to the flag file. For example, it might print /path/to/a/very/deep/flag_file.

Your goal is to read this file. Since you cannot cd into the /path/to/a/very/deep/ directory, you cannot use a simple relative command like cat flag_file.

The only viable method is to give the cat command the exact, absolute path that the challenge provided you. You simply need to copy the path and use it as an argument for cat.

```bash
hacker@commands~more-catting-practice:~$ cat /usr/lib/git-core/flag
pwn.college{IJJuluY9bMj8uLLuGYEKknA_0G4.QXwITO0wSN0AzNzEzW}
```
    
### New Learning
Even without the ability to cd into a directory, you can still access files inside it using their absolute paths.

This reinforces the concept that commands can operate on any file in the file system, not just those in the immediate vicinity.

### References 
None