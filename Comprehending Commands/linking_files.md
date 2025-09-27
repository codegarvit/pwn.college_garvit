# pwn.college_garvit
# Comprehending Commands

# Linking Files
This challenge introduces symbolic links (also known as symlinks or soft links), a powerful feature for creating shortcuts or pointers to other files and directories. The scenario involves a program, /challenge/catflag, that is broken. It's supposed to read the flag from /flag but instead reads from an incorrect path, /home/hacker/not-the-flag. The goal is to use a symlink to trick the program into reading the correct file.

### Solve
**Flag:** `pwn.college{cx6ZWSROHNWS-rK3FW6F64VDZWU.QX5ETN1wSN0AzNzEzW}`

The solution is to replace the incorrect path with a symbolic link that points to the real flag file. This redirects the program's file access without modifying the program itself.

1. Create the Symbolic Link: The ln -s command is used to create the link. The syntax is ln -s <target> <link_name>.
The target is the real file we want to point to: /flag.
The link_name is the path the broken program is trying to access: /home/hacker/not-the-flag.

2. Run the Program: With the link in place, the /challenge/catflag program is executed.
When the program attempts to open /home/hacker/not-the-flag, the operating system follows the symbolic link, transparently redirecting it to read the contents of /flag, which reveals the flag.

```bash
hacker@commands~linking-files:~$ ln -s /flag /home/hacker/not-the-flag
hacker@commands~linking-files:~$ /challenge/catflag
About to read out the /home/hacker/not-the-flag file!
pwn.college{cx6ZWSROHNWS-rK3FW6F64VDZWU.QX5ETN1wSN0AzNzEzW}
```
    
### New Learnings

1. Creating Symlinks: The main lesson is the usage of ln -s <target_file> <link_name> to create symbolic links. This is a fundamental command for filesystem management.

2. Filesystem Redirection: This challenge demonstrates a key use case for symlinks: redirecting file access. It's a common technique for managing different versions of software or libraries without needing to change hardcoded paths in programs.

3. How Symlinks Function: A symlink is a special type of file that simply contains a path to another file or directory. When an application tries to access the symlink, the operating system automatically follows the path to the target location.

### References 
None