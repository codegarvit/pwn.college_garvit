# pwn.college_garvit
# Chaining Commands

# Building On Success
This challenge shows how to use exit codes to "chain commands together" with the && operator. The && operator "allows you to run a second command only if the first command succeeds". The task is to "chain the programs /challenge/first-success and /challenge/second using the && operator" to get the flag.

### Solve
**Flag:** `pwn.college{ITW61rl8pOpfe9EtY880IeBX7mk.0lM0MDOxwSN0AzNzEzW}`
The solution requires us to place both program names on a single line, connected by the && operator, as described in the challenge.

1. The Goal: We need to run /challenge/first-success and, only if it succeeds, then run /challenge/second.

2. The Tool: The challenge introduces the && operator. The syntax command1 && command2 means, "Run command1, and IF it succeeds, then run command2".

3. The Final Command: We build the command by putting the two programs in order, separated by the && operator.

4. The Result: The /challenge/first-success command is designed to succeed (exit with code 0). Because the first command succeeds, the && operator allows the second command, /challenge/second, to run. This prints the flag.

```bash
hacker@chaining~building-on-success:~$ /challenge/first-success && /challenge/second
Nice chaining! Flag: pwn.college{ITW61rl8pOpfe9EtY880IeBX7mk.0lM0MDOxwSN0AzNzEzW}
```
    
### New Learnings
1. The && Operator: The main lesson is the && operator, which we can use to "run a second command only if the first command succeeds".

### References 
None