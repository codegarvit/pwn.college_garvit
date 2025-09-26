# pwn.college_garvit
# Hello Hackers

# Home Sweet Home
Every user on a Linux system has a home directory (usually under /home). In the dojo you are the hacker user and your home directory is /home/hacker. Bash provides the shorthand ~ to mean your home directory; whenever ~ appears at the start of an argument in a way that looks like a path, the shell expands it to the full absolute path /home/hacker.

### Solve
**Flag:** `pwn.college{EcP8uW5fhPOZ3s8ZMcckt_4tR8p.QXzMDO0wSN0AzNzEzW}`
We need to run the /challenge/run program with a file path as an argument that meets three specific constraints.
The key to this challenge is using the ~ (tilde) character, which the instructions explain is a shorthand for your home directory (/home/hacker).
The Constraints
1. The path must be an absolute path.
2. The path must be inside your home directory.
3. The argument you type must be three characters or less.

The Solution
1. The path ~/a meets all the requirements:
2. It is three characters long (~, /, a).
3. The shell expands the ~ to /home/hacker, making the final path /home/hacker/a. This is an absolute path and is inside your home directory.
Therefore, running the following command:
```bash
hacker@paths~home-sweet-home:~$ /challenge/run ~/a
Writing the file to /home/hacker/a!
... and reading it back to you:
pwn.college{EcP8uW5fhPOZ3s8ZMcckt_4tR8p.QXzMDO0wSN0AzNzEzW}
```
    
### New Learnings
The key takeaways are:

1. ~ is a shell shorthand for your home directory; the shell expands it before calling a program.
2. Only a leading ~ (at the beginning of the argument) is expanded. ~/x → /home/hacker/x. /~ does not expand to your home.
3. You can exploit the expansion step to meet constraints on what you type while still producing an asolute path after expansion.
4. cd with no argument returns you to ~ (your home).

### References 
None