# pwn.college_garvit
# File GLobbing

# Tab Completion
This challenge introduces Tab completion, a fundamental and powerful feature of the shell that increases speed and prevents typing errors. The task is to read a flag from a file located at /challenge/pwncollege. However, the challenge creator has used "trickery" to modify the filename with hidden or un-typable characters, making it impossible to access by typing the name manually. The solution requires using the Tab key to auto-complete the correct path

### Solve
**Flag:** `pwn.college{wq_htMylt1pBu5-_ZVKyfrJvZ2z.0FN0EzNxwSN0AzNzEzW}`

The solution is to let the shell do the work of finding and typing the correct filename.

1. Start Typing: Begin by typing the cat command and the partial path to the file. 

2. Use Tab Completion: With the partial command typed, press the Tab key. The shell automatically finds the unique file that matches the prefix and completes the rest of the filename, including any hidden special characters.

3. Execute the Command: After the shell auto-completes the path, the full command is now on the line. Simply press Enter to run the cat command and display the flag.

```bash
hacker@globbing~tab-completion:~$ cat /challenge/pwncollege​
pwn.college{wq_htMylt1pBu5-_ZVKyfrJvZ2z.0FN0EzNxwSN0AzNzEzW}
```
    
### New Learnings
1. The Power of Tab Completion: The primary lesson is the importance of using the Tab key to auto-complete commands and paths. It is one of the most useful and frequently used features of the shell for both speed and accuracy.

2. Handling Complex Filenames: Tab completion is not just a convenience; it's essential for working with files that have spaces, special characters, or non-printable characters in their names. It's the only reliable way to ensure you are targeting the correct file.

3. Shell Interactivity: This challenge demonstrates that the shell is an interactive assistant. It can actively help you construct commands correctly, saving you time and preventing errors.

### References 
None