# pwn.college_garvit
# File GLobbing

# Multiple Tabs for Tab Completion
This challenge teaches how to handle Tab completion when multiple file or command names match the typed prefix. It explains that in the bash shell, pressing Tab once will auto-complete up to the common part of all matches. Pressing Tab a second time will display a list of all possible completions. The task is to use this "double-tab" technique to navigate a directory structure under /challenge/files, where many files share a common prefix, to find and read the flag file.

### Solve
**Flag:** `pwn.college{0x58U0QQIiPMbr_xX6RGZf1_5iz.0lN0EzNxwSN0AzNzEzW}`
The solution is an iterative process of building the file path by using Tab completion to both complete parts of the name and discover the next part of the path.

1. Start the Command: Begin by typing the initial part of the path.

2. Navigate with Tab: From the list, the most likely target is pwncollege-flag. This path is built piece by piece:
Type c and press Tab. The shell auto-completes the path to /challenge/files/pwncollege.
Type f and press Tab again. The shell auto-completes the full path to /challenge/files/pwncollege-flag.

3. Get the Flag: With the complete and correct path on the command line, press Enter to execute the cat command and display the flag.

```bash
hacker@globbing~multiple-options-for-tab-completion:~$ cat /challenge/files/pwn
pwn                    pwn-the-planet         pwncollege-flag        pwncollege-flyswatter
pwn-college            pwncollege-family      pwncollege-flamingo    pwncollege-hacking
hacker@globbing~multiple-options-for-tab-completion:~$ cat /challenge/files/pwncollege-flag
pwn.college{0x58U0QQIiPMbr_xX6RGZf1_5iz.0lN0EzNxwSN0AzNzEzW}
```
    
### New Learnings
1. Efficiency and Accuracy: The process of typing just enough characters to create a unique prefix and then pressing Tab is significantly faster and less prone to typos than manually typing long, complex names.

2. The "Double-Tab" Feature: The core lesson is the behavior of Tab completion in bash. Pressing Tab once completes to the longest common prefix, while pressing it a second time lists all possibilities. This is a fundamental feature for interactive shell us

### References 
None