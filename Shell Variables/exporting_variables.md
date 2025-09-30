# pwn.college_garvit
# Shell Variables

# Exporting Variables
This challenge teaches the difference between local shell variables and environment variables. It introduces the export command, which makes a variable available to any child processes that are started from the current shell. The task is to set two variables: one that is exported and one that is not, and then run a verification program.

### Solve
**Flag:** `pwn.college{ALoUe1_58c1ZTQ7tQzHVcTL9elx.QXyYTN0wSN0AzNzEzW}`
The goal is to invoke /challenge/run in an environment where the variable PWN is set to COLLEGE and is exported, while the variable COLLEGE is set to PWN but is not exported.

1.  Set the Exported Variable: To set a variable and mark it for export in a single step, the export VAR=value syntax is used. This ensures the /challenge/run program will inherit the PWN variable.

2. Set the Local Variable: To create a variable that is only visible in the current shell, the standard assignment syntax is used without the export command. This ensures /challenge/run will not inherit the COLLEGE variable.

3. Run the Verifier: With the environment correctly configured, the /challenge/run program is executed. It checks its inherited variables, finds that PWN is present with the correct value and COLLEGE is absent, and then prints the flag.
```bash
hacker@variables~exporting-variables:~$ export PWN=COLLEGE
You've set the PWN variable to the proper value!
hacker@variables~exporting-variables:~$ COLLEGE=PWN
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
hacker@variables~exporting-variables:~$ /challenge/run
CORRECT!
You have exported PWN=COLLEGE and set, but not exported, COLLEGE=PWN. Great
job! Here is your flag:
pwn.college{ALoUe1_58c1ZTQ7tQzHVcTL9elx.QXyYTN0wSN0AzNzEzW}
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
```
    
### New Learnings
1. Local vs. Environment Variables: The primary lesson is the distinction between local variables, which exist only within the current shell, and environment variables, which are passed down to any child processes that shell creates.

2. The export Command: This challenge teaches that the export command is the mechanism for promoting a local variable to an environment variable, making it inheritable.

### References 
None