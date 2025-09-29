# pwn.college_garvit
# Digesting Documentation

# Moving Files
This challenge emphasizes a fundamental skill for using any command-line program: reading its documentation to understand the correct arguments. The task involves a program, /challenge/challenge, which will only yield a flag if run correctly. The challenge description itself provides a small block of "documentation" that explicitly states the required argument.

### Solve
**Flag:** `pwn.college{4BDRWBpyp8kqW5PTa3SkfOKGSzY.QX0ITO0wSN0AzNzEzW}`

The solution is a direct application of the information provided in the challenge's "documentation" block.
1. Read the Documentation: The prompt contains the key to the solution:
"To properly run this program, you will need to pass it the argument of --giveflag."

2. Execute the Command: The program is run with the exact argument specified. It's crucial to be precise, as a common mistake is to type --give-flag (with a hyphen) instead of the correct --giveflag (one word).

```bash
hacker@man~learning-from-documentation:~$ /challenge/challenge --giveflag
Correct argument! Here is your flag:
pwn.college{4BDRWBpyp8kqW5PTa3SkfOKGSzY.QX0ITO0wSN0AzNzEzW}
```
    
### New Learnings

1. Documentation is Key: The primary lesson is that the first step to understanding an unfamiliar program is to check its documentation (such as --help output, man pages, or a README file).

2. Precision Matters: This challenge highlights that command-line arguments must be typed exactly as specified. A minor typo, like an extra hyphen or a spelling mistake, will often cause the program to fail or behave unexpectedly.

3. Command-Line Arguments: This is a practical example of how arguments (especially those starting with --, often called "options" or "flags") are used to control a program's execution flow.

### References 
None