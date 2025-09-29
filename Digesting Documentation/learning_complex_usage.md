# pwn.college_garvit
# Digesting Documentation

# Moving Files
This challenge introduces a common pattern in command-line tools: arguments that take their own arguments. Using find -name <filename> as an example, it explains that an option (like -name) can require additional information. The task is to use a program, /challenge/challenge, whose documentation specifies a --printfile option that takes a file path as its own argument. The goal is to use this feature to print the system's flag.    

### Solve
**Flag:** `pwn.college{s_qsjs4EjOAuQ8pOUjt-2L0NOaI.QX1ITO0wSN0AzNzEzW}`

The solution requires constructing a command that follows the structure described in the challenge's documentation.
1. Analyze the Documentation: The prompt explains that to print a file, you must use the --printfile argument, followed by the path of the file to print.

2. Identify the Target: The file we want to print is the flag. Based on convention in pwn.college, the flag is located at the absolute path /flag.

3. Construct the Command: The final command is built by combining the program's name, the required option, and the argument to that option (the path to the flag).

```bash
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile /flag
Correct argument! Here is the /flag file:
pwn.college{s_qsjs4EjOAuQ8pOUjt-2L0NOaI.QX1ITO0wSN0AzNzEzW}
```
    
### New Learnings

1. Arguments to Arguments: The primary lesson is that command-line options often require their own arguments. This [command] [option] [argument_for_option] structure is a fundamental pattern in many powerful tools.

2. Reading Documentation for Structure: This challenge reinforces the idea that documentation doesn't just tell you what arguments exist, but also how they are structured and used together.

3. Inferring Target Paths: In many challenges, you must infer standard file locations. Knowing that the flag is typically at /flag is a key piece of contextual knowledge for solving this and many similar problems.

### References 
None