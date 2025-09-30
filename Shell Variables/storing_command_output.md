# pwn.college_garvit
# Shell Variables

# Storing Command Output
This challenge introduces Command Substitution, a shell feature that captures the output of a command so it can be stored in a variable. The task is to execute the /challenge/run program and store its output directly into a variable named PWN.

### Solve
**Flag:** `pwn.college{kTX6l2sbuhYDndA5iogxy67upCx.QX1cDN1wSN0AzNzEzW}`
The solution requires using the $(command) syntax for command substitution to capture the output, and then using echo to display the contents of the variable.

1. The Goal: The challenge requires you to capture the output of /challenge/run and store it in a variable named PWN.

2. The Technique: The prompt explains that the syntax $(command) is used for command substitution. The shell runs the command inside the parentheses, captures its output, and substitutes the entire expression with the resulting text. This can then be assigned to a variable.

3. The Final Commands: The process involves two steps: first capturing the output, then printing it.
This command runs /challenge/run, and its output (the flag) is stored in the PWN variable.
PWN=$(/challenge/run)

This command uses echo and variable expansion ($PWN) to print the contents of the PWN variable to the screen, revealing the flag.
echo $PWN

```bash
hacker@variables~storing-command-output:~$ PWN=$(/challenge/run)
Congratulations! You have read the flag into the PWN variable. Now print it out
and submit it!
hacker@variables~storing-command-output:~$ echo $PWN
pwn.college{kTX6l2sbuhYDndA5iogxy67upCx.QX1cDN1wSN0AzNzEzW}
```
    
### New Learnings
1. Command Substitution $(...): The main lesson is using the $(command) syntax to capture the standard output of a command. This is a fundamental technique in shell scripting for using the results of one command as data in another.

2. Backtick Syntax: The challenge also mentions the older, alternative syntax for command substitution using backticks (`command`), while recommending the modern $(...) form for better readability and nesting capabilities.
### References 
None