# pwn.college_garvit
# Digesting Documentation

# Reading Manuals
This challenge introduces the fundamental man (manual) command, which is used to display the documentation for command-line programs. The task is to use the man command to learn about a custom program and by reading its manual, you must find the specific option and argument required to make it print the flag.  

### Solve
**Flag:** `pwn.college{4XeqqJEEJ1oSNjyPj9vHT4Hw0hm.QX0EDO0wSN0AzNzEzW}`

The solution path is a direct application of the skills taught in the level: finding and correctly applying information from a manual page.
1. Open the Manual: The first step is to view the manual for the program. The challenge instructions clarify that man takes the name of a command, not its full path.

2. Find the Secret Option: Reading the DESCRIPTION section of the displayed manual page reveals the exact option and argument needed to get the flag:
--eqqojv NUM: print the flag if NUM is 419

3. Execute the Command: The final step is to run the program with the precise option and argument discovered in the manual.

```bash
hacker@man~reading-manuals:~$ man challenge
hacker@man~reading-manuals:~$ /challenge/challenge --eqqojy 419
Correct usage! Your flag: pwn.college{4XeqqJEEJ1oSNjyPj9vHT4Hw0hm.QX0EDO0wSN0AzNzEzW}
```
    
### New Learnings
1. Using the man Command: The core lesson is how to use man <command_name> to access detailed documentation for tools on a Linux system.

2. Structure of Man Pages: The challenge familiarizes you with the standard sections of a manual page, such as NAME (what it is), SYNOPSIS (how to use it), and DESCRIPTION (details about its options).

### References 
None