# pwn.college_garvit
# Comprehending Commands

# Listing Files
This challenge teaches how to list the contents of a directory. A file with a random name has been placed inside /challenge. The goal is to use the ls command to find the name of this file.

### Solve
**Flag:** `pwn.college{UNqZYkzsYkt1j-5D9wecAQNrboq.QX5ETO0wSN0AzNzEzW}`

The problem is that you need to read a file, but you don't know its name. This is a classic "reconnaissance" or information-gathering step.

The fundamental command for seeing the contents of a directory is ls (short for "list").

By default, ls on its own lists files in your current directory. To look inside a different directory, you must provide its path as an argument.

The command ls /challenge tells the shell: "List the contents of the /challenge directory." The output will be the name of the randomly-named file.

Once you have the filename (e.g., aBcDeFg), you can proceed to the next step of reading it with cat /challenge/aBcDeFg.

```bash
hacker@commands~cat-not-the-pet-but-the-command:~$ cat /flag
pwn.college{UNqZYkzsYkt1j-5D9wecAQNrboq.QX5ETO0wSN0AzNzEzW}
```
    
### New Learnings

1. The ls command lists the contents of a directory.
2. If you provide a path as an argument (e.g., ls /challenge), it lists the contents of that directory.
3. If no arguments are given, ls lists the contents of the current working directory.

### References 
None