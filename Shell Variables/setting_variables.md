# pwn.college_garvit
# Shell Variables

# Setting Variables
This challenge teaches the syntax for setting, or assigning a value to, a shell variable. The task is to create a variable named PWN and assign it the specific string value COLLEGE, paying close attention to the case-sensitive names and the required syntax.  

### Solve
**Flag:** `pwn.college{4EAC85o3PvOWKxGuVD7c7qv-jya.QX5UTN0wSN0AzNzEzW}`
The solution requires applying the exact variable assignment syntax demonstrated in the challenge prompt. The challenge environment automatically detects when the variable has been set correctly and provides the flag.

1. The Goal: The challenge explicitly requires you to set the variable PWN to the value COLLEGE.

2. The Syntax: The prompt teaches that the syntax for variable assignment is VAR=value and highlights two critical rules:
 - There must be no spaces around the = sign.
 - The $ prefix is not used when assigning a value to a variable; it's only for reading the value.

3. The Final Command: The command is constructed by following these rules precisely, using the case-sensitive names provided in the prompt.
Once this command is executed, the PWN variable is correctly set in the shell's environment, and the challenge is solved.

```bash
hacker@variables~setting-variables:~$ PWN=COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{4EAC85o3PvOWKxGuVD7c7qv-jya.QX5UTN0wSN0AzNzEzW}
```
    
### New Learnings
1. Variable Assignment Syntax: The primary lesson is the correct syntax for setting shell variables, VAR=value, and the critical rule of having no spaces around the equals sign (=).

2. Setting vs. Reading Variables: The challenge clearly distinguishes between the syntax for setting a variable (VAR=...) and reading or expanding a variable ($VAR). This is a fundamental concept in shell scripting.

3. Case Sensitivity: The prompt explicitly notes that both variable names and their string values are case-sensitive (e.g., PWN is different from pwn), which is a crucial rule in most programming and scripting languages.

### References 
None