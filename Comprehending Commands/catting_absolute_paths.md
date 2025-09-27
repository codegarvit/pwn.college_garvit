# pwn.college_garvit
# Comprehending Commands

# Catting Absolute Paths
The challenge requires reading a flag file. Unlike previous levels where the file might be in the current (home) directory, this time it's located at the absolute path /flag. The task is to use the cat command with this absolute path to display its contents.

### Solve
**Flag:** `pwn.college{UNqZYkzsYkt1j-5D9wecAQNrboq.QX5ETO0wSN0AzNzEzW}`

The key to this challenge is understanding the difference between a relative and an absolute path.

A relative path (like flag) is interpreted from your current location. If you were in the / directory, cat flag would work. But you start in your home directory (~), where there is no file named flag, so cat flag would fail.

An absolute path starts with /, which represents the root of the entire filesystem. It provides a complete, unambiguous location for a file.

Therefore, to access the file from anywhere, you must provide the command cat with the file's full address. The command cat /flag instructs the shell to start at the root directory /, find the file named flag inside it, and print its contents.

```bash
hacker@commands~cat-not-the-pet-but-the-command:~$ cat /flag
pwn.college{UNqZYkzsYkt1j-5D9wecAQNrboq.QX5ETO0wSN0AzNzEzW}
```
    
### New Learnings
An absolute path is a file or directory location that starts from the root directory (/).

Commands like cat can operate on files anywhere in the system if an absolute path is provided (and you have the necessary permissions).

Using an absolute path works regardless of your current working directory.

### References 
None