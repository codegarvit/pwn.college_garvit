# pwn.college_garvit
# Chaining Commands

# Chaining With Semicolons
This challenge covers the "easiest way to chain commands" by using a semicolon (;). The semicolon "separates commands in a similar way to how Enter separates lines," allowing multiple commands to be run in sequence from a single line. The task is to "run /challenge/pwn and then /challenge/college, chaining them with a semicolon".

### Solve
**Flag:** `pwn.college{Ys_cpu6TT20MngCKf5UTANinFJP.QX1UDO0wSN0AzNzEzW}`
The solution requires us to place both commands on a single line, separated by a semicolon, as described in the challenge.

1. The Goal: We must run two commands, /challenge/pwn and /challenge/college, in that specific order.

2. The Tool: The challenge introduces the semicolon (;) as the tool to chain commands.

3. The Final Command: The two commands are typed on one line with a semicolon between them.

4. The Result: The shell executes /challenge/pwn, and after that command terminates, it immediately executes /challenge/college, which prints the flag.

```bash
hacker@chaining~chaining-with-semicolons:~$ /challenge/pwn ; /challenge/college
Yes! You chained /challenge/pwn and /challenge/college! Here is your flag:
pwn.college{Ys_cpu6TT20MngCKf5UTANinFJP.QX1UDO0wSN0AzNzEzW}
```
    
### New Learnings
1. Use Case: This is a simple way to run a sequence of commands without needing to wait for each one to finish before typing the next command.

2. The Semicolon Separator: The main lesson is that a semicolon (;) can be used to separate commands on a single line, and the shell will execute them one after the other.

### References 
None