# pwn.college_garvit
# Comprehending Commands

# hidden Files
This challenge introduces the concept of "hidden" files in Linux, which are files whose names begin with a dot (.). These files are not displayed by the ls command by default. The task is to use the -a flag with ls to find a hidden flag file in the root directory (/) and then read its contents.

### Solve
**Flag:** `pwn.college{goryZNX3x92aQFH0bPLstxZtNbH.QXxcTN0wSN0AzNzEzW}`

The solution is a two-step process: first, discover the hidden filename, and second, read the contents of that file.

1. Finding the Hidden File: The prompt explains that the ls command needs the -a (all) flag to show hidden files. This flag is used to list the contents of the root directory (/).

2. This command's output reveals all files, including the hidden flag file, which was named flag-180601817825851.

3. Reading the Flag: Once the full name of the hidden file is known, the cat command is used with the file's absolute path to display its contents, which is the flag.

```bash
hacker@commands~hidden-files:~$ ls -a /
.   .dockerenv             bin   challenge  etc   lib    lib64   media  nix  proc  run   srv  tmp  var
..  .flag-180601817825851  boot  dev        home  lib32  libx32  mnt    opt  root  sbin  sys  usr
hacker@commands~hidden-files:~$ cat /.flag-180601817825851
pwn.college{449TLA3JLDtYHEMTWUXPd3FhEA8.QXwUDO0wSN0AzNzEzW}
```
    
### New Learnings
1. Hidden Files (Dotfiles): The primary lesson is the convention in Linux where prefixing a filename with a dot (.) makes it "hidden" from default listings. These are often used for user-specific configuration files (e.g., .bashrc).

2. The ls -a Command: The challenge directly teaches the use of the -a flag for the ls command, which is the standard way to make hidden dotfiles visible in a directory listing.

### References 
None