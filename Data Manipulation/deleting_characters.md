# pwn.college_garvit
# Data Manipulation

# Deleting Characters
This challenge introduces the -d (delete) flag for the tr command, which is used to remove specific characters from a stream of text. The task is to clean the output of a program that prints the flag mixed with decoy characters, specifically ^ and %.

### Solve
**Flag:** `pwn.college{gBDWqLTavOc5VnhxpYHNXFinScx.0FNxEzNxwSN0AzNzEzW}`

The solution requires piping the scrambled output of the challenge program into a tr command configured to delete the unwanted characters.
1. The Goal: The /challenge/run program outputs a flag that is unreadable because it is interspersed with ^ and % characters. These must be removed.

2. The Tool: The challenge specifies using the tr command with the -d flag to delete characters.

3. Command Construction: A pipeline is created to solve the problem in one step.
 - The /challenge/run command is executed to produce the output.
 - The pipe (|) sends this output directly to the tr command.
 - The tr -d '%^' command receives the text. The -d flag activates delete mode, and the argument '%^' tells tr to remove every instance of % and ^. The quotes are used to ensure the ^ is treated as a literal character.

```bash
hacker@data~deleting-characters:~$ /challenge/run | tr -d '%^'
Your character-stuffed flag:
pwn.college{gBDWqLTavOc5VnhxpYHNXFinScx.0FNxEzNxwSN0AzNzEzW}
```
    
### New Learnings
The tr -d Option: The core lesson is the use of the -d flag with tr to delete all occurrences of a specified set of characters from standard input.

Handling Special Characters in Arguments: Using quotes around the argument ('%^') is an important practice. It prevents the shell from interpreting special characters (like ^) in unintended ways and ensures they are passed literally to the command.

### References 
None