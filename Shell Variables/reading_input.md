# pwn.college_garvit
# Shell Variables

# Reading Input
This challenge introduces the read shell builtin, which is used to read a line of text from standard input (the keyboard) and store it into a variable. The task is to use the read command to set a variable named PWN to the specific value COLLEGE.

### Solve
**Flag:** `pwn.college{4EAC85o3PvOWKxGuVD7c7qv-jya.QX5UTN0wSN0AzNzEzW}`
The solution is an interactive two-step process that involves telling the shell to wait for input and then providing the correct value.

1. Initiate the read Command: The first step is to execute the read command, providing the name of the variable where the input should be stored. This tells the shell to pause and wait for the user to type a line of text.


2. Provide the Input: The terminal will now be waiting on a new line for input. The user must type the required value, COLLEGE, and then press Enter to submit it. Once Enter is pressed, the shell assigns the typed string "COLLEGE" to the PWN variable, solving the challenge.



```bash
hacker@variables~reading-input:~$ read PWN
COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{QQw7FQzdzSNuKLe2u_FTVkxYfD3.QX4cTN0wSN0AzNzEzW}
```
    
### New Learnings
1. The read Builtin: The primary lesson is how to use the read <VARNAME> command to capture user input from the keyboard and store it in a shell variable. This is a fundamental tool for creating interactive shell scripts.

2. Standard Input (stdin): This challenge demonstrates the default behavior of standard input, which is to read from the keyboard. While previous challenges showed how to redirect a file into stdin with <, this shows how commands read from it interactively.
### References 
None