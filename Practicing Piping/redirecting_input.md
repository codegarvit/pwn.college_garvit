# pwn.college_garvit
# File GLobbing

# Redirecting Intput
This challenge introduces redirecting standard input (stdin) using the < character, which allows a program to read from a file as if it were receiving input from the keyboard. 

### Solve
**Flag:** `pwn.college{sF0is3f2lM2777PPgv7XoASvUQL.QXwcTN0wSN0AzNzEzW}`
The solution requires two separate commands to first prepare the input file and then run the challenge with that file as its input.

1. Create the Input File: The echo command is used with output redirection (>) to create a file named PWN with the required content, "COLLEGE".

2. Run with Input Redirection: The /challenge/run program is executed. The < operator tells the shell to feed the contents of the PWN file into the program's standard input, which solves the challenge.

```bash
hacker@piping~redirecting-input:~$ echo COLLEGE > PWN
hacker@piping~redirecting-input:~$ /challenge/run < PWN
Reading from standard input...
Correct! You have redirected the PWN file into my standard input, and I read
the value 'COLLEGE' out of it!
Here is your flag:
pwn.college{sF0is3f2lM2777PPgv7XoASvUQL.QXwcTN0wSN0AzNzEzW}
```
    
### New Learnings
1. The < Input Redirection Operator: The core lesson is that the < operator is used to redirect the contents of a file into a command's standard input.

2. Standard Input (stdin): This challenge provides a practical demonstration of the standard input stream. Many command-line programs are designed to read data from stdin, and this feature allows you to easily provide that data from a file.

3. Combining I/O Redirection: The solution requires using both output redirection (>) to prepare the data file and input redirection (<) to use it. This shows how different shell redirection features are often used together to accomplish a task.

### References 
None